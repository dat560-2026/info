# Variational Autoencoder: implementation guide.

You need to implement the missing methods in the given skeleton in student/vae.py of the assignment repo.

---

## 1. Goal of the model

We model data `x` using a latent variable `z`:

p(x) = ∫ p(x | z) p(z) dz

This marginal likelihood is intractable. We introduce an approximate posterior
qφ(z | x) and apply Jensen’s inequality:

log p(x) ≥ Eqφ(z|x)[ log pθ(x | z) ] − KL(qφ(z|x) || p(z))

The right-hand side is the **Evidence Lower Bound (ELBO)**.

Training a VAE means **maximizing the ELBO**, or equivalently **minimizing −ELBO**.

---

## 2. Encoder: implementing qφ(z | x)

### Theory
We choose a diagonal Gaussian posterior:

qφ(z | x) = 𝒩( μ(x), diag(σ²(x)) )

The encoder must output:
- μ(x): mean of the latent distribution
- log σ²(x): log-variance (for numerical stability)

### Skeleton components
- `self.enc`: maps x → hidden representation
- `self.mu`: maps hidden → μ(x)
- `self.logvar`: maps hidden → log σ²(x)

### encode(x)
Should:
1. Pass x through `self.enc`
2. Produce μ and log σ²
3. Return both

---

## 3. Reparameterization trick

### Theory
We need to sample z ~ qφ(z | x) but still allow gradients.

Rewrite sampling as:
z = μ + σ ⊙ ε,   ε ~ 𝒩(0, I)

This moves randomness into ε and keeps μ, σ differentiable.

### reparameterize(mu, logvar)
Should:
1. Convert log σ² → σ
2. Sample ε from a standard normal
3. Construct z using the formula above

---

## 4. Decoder: implementing pθ(x | z)

### Theory
The decoder parameterizes the likelihood pθ(x | z).

Common choices:
- Bernoulli likelihood for binary or normalized inputs
- Gaussian likelihood for continuous inputs

The skeleton uses logits so that:
- Bernoulli likelihood uses sigmoid internally
- Gaussian/L1 losses can still be derived

### decode(z)
Should:
- Map latent variable z back to reconstruction parameters for x

---

## 5. Forward pass: Monte Carlo estimate of ELBO

### Theory
The expectation Eqφ(z|x)[log p(x|z)] is approximated using Monte Carlo sampling.
In practice, one sample per datapoint is enough.

### forward(x)
Should:
1. Encode x → μ, log σ²
2. Sample z using reparameterization
3. Decode z → logits
4. Return all intermediate values needed for the ELBO

---

## 6. KL divergence term

### Theory
The prior is fixed:

p(z) = 𝒩(0, I)

The KL divergence between two diagonal Gaussians has a closed form:

KL(q||p) = ½ Σ ( μ² + σ² − log σ² − 1 )

This term:
- Penalizes deviation from the prior
- Regularizes the latent space

### kl_divergence(mu, logvar)
Should:
- Implement the closed-form KL
- Average over the batch

---

## 7. Reconstruction loss

### Theory
The reconstruction term is the negative log-likelihood:

−Eqφ(z|x)[log pθ(x | z)]

Depending on likelihood choice:
- Bernoulli → Binary cross entropy
- Gaussian → Mean squared error
- Laplace → L1 loss

### reconstruction_loss_*
Each function should:
- Compute a summed loss over features
- Average over the batch
- Match a valid likelihood interpretation

---

## 8. ELBO computation

### Theory
ELBO:

ELBO = Eq[log p(x|z)] − β · KL(q||p)

Training objective:

loss = −ELBO = reconstruction_loss + β · KL

β = 1 gives the standard VAE.
β > 1 gives a β-VAE with stronger regularization.

### compute_elbo(...)
Should:
1. Select reconstruction loss based on `recon_loss`
2. Compute KL divergence
3. Combine them into total loss
4. Return all components separately

---

## 9. β scheduling

### Theory
Early in training, the KL term can dominate and collapse the latent space.
A common fix is to slowly increase β from 0 to β_max.

### beta_schedule(...)
Should:
- Increase β linearly during warmup
- Stay constant after warmup

---

## 10. Loss wrapper and model construction

### vae_loss(...)
Simply calls `compute_elbo` for clarity and consistency.

### build_model(cfg)
Should:
- Instantiate a VAE using the configuration object
- Pass architectural and loss-related parameters

---

## General guidelines

- **Check tensor shapes carefully.**
  - `x`: `(batch_size, input_dim)`
  - `mu`, `logvar`, `z`: `(batch_size, latent_dim)`
  - `logits`: `(batch_size, input_dim)`
  - Losses should be scalars.

- **Use “sum over dimensions, mean over batch”.**
  This keeps loss magnitudes stable across batch sizes.

- **Do not apply sigmoid twice.**
  - Bernoulli reconstruction expects logits.
  - Sigmoid should only be applied where required by the loss.

- **KL should never be negative.**
  If it is, there is a bug.

- **If KL quickly goes to zero and stays there**, the model may be ignoring the latent variable.

- **Start simple.**
  Use small latent dimensions and verify each component independently.

- **Make small commits**
  Every commit the Github action is run which runs tests and gives scores. Try to pass local tests first then the hidden tests. Most bugs are local and easier to debug early. 

If you can explain which term of the ELBO a function implements, you are on the right track.

# Assignment Guide: Implementing a Decoder-Only Character-Level LLM for English-to-Klingon Translation

## Overview
In this assignment, you will build a decoder-only transformer language model (LLM) that operates at the character level. Your model will be trained to translate English text into Klingon using a provided dataset. You will implement core components of the transformer architecture and supporting utilities, then train and evaluate your model.

## Objectives
- Implement a character-level tokenizer
- Build the core transformer components: attention, transformer blocks, feed-forward layers
- Assemble a decoder-only transformer model
- Train the model on English-to-Klingon data
- Evaluate and generate translations

## Dataset
The dataset consists of paired English and Klingon sentences, formatted for character-level modeling. You will find the training data in `data/klingon_translation_train.txt`.

## Implementation Parts
### 1. Character Tokenizer
- **Purpose:** Converts text into sequences of character indices and vice versa.
- **Tasks:**
  - Build vocabulary from dataset characters
  - Implement `encode(text)` and `decode(indices)` methods

### 2. Attention Mechanism
- **Purpose:** Allows the model to focus on relevant parts of the input sequence.
- **Tasks:**
  - Implement scaled dot-product attention
  - Apply causal masking so each position only attends to previous positions

### 3. Transformer Block
- **Purpose:** The main building block of the model, combining attention and feed-forward layers.
- **Tasks:**
  - Implement multi-head self-attention
  - Add layer normalization and residual connections
  - Implement position-wise feed-forward network

### 4. Feed-Forward Layer
- **Purpose:** Applies non-linear transformations to each position independently.
- **Tasks:**
  - Two linear layers with activation (e.g., ReLU)
  - Dropout for regularization

### 5. Positional Encoding
- **Purpose:** Injects information about the position of each character in the sequence.
- **Tasks:**
  - Implement learnable or sinusoidal positional embeddings

### 6. Decoder-Only Transformer Model
- **Purpose:** Assembles the above components into a full model for sequence generation.
- **Tasks:**
  - Stack multiple transformer blocks
  - Output logits for each character position

### 7. Training Loop
- **Purpose:** Optimizes the model parameters using the dataset.
- **Tasks:**
  - Prepare data loaders for train/validation splits
  - Implement loss computation (cross-entropy)
  - Save model checkpoints
  - Track and plot training/validation loss

### 8. Generation & Evaluation
- **Purpose:** Generate Klingon translations from English prompts and evaluate model performance.
- **Tasks:**
  - Implement greedy or sampling-based generation
  - Decode output indices to text
  - Evaluate translation quality
ed

## Tips
- There is already some code given to you and you only need to implement missing parts
- Start by implementing and testing each component in isolation
- Use small batches and context lengths for initial debugging
- Visualize training and validation loss to monitor progress
- Save and test your model frequently

## References
- [Attention Is All You Need](https://arxiv.org/abs/1706.03762)
- PyTorch documentation: https://pytorch.org/docs/stable/index.html

Good luck, and Qapla'!

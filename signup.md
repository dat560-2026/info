# Signing up to DAT560 Generative AI

In this course we use GitHub Classroom for distributing assignments and collecting submissions. Your submission is your Git history on GitHub: you push commits, the autograder runs automatically.

## 1) Create the right GitHub account (do this first)

1. Go to https://github.com and create a GitHub account (or use an existing one).
2. **Add your university student email address** to your GitHub account:
   - GitHub → Settings → Emails → Add email
   - Add your *student email address* and verify it.
3. Pick the GitHub account you will use for this course and **stick with it**.
   - **No switching accounts later.**
   - **No username changes later.**
   - Your GitHub account must match the roster entry you will select in GitHub Classroom.

Why so strict? GitHub Classroom links your GitHub account to the course roster for tracking and grading. This linking happens when you join/accept an assignment.  [The GitHub Blog](https://github.blog/developer-skills/github-education/set-up-your-digital-classroom-with-github-classroom/)

## 2) Accept the course invitations (watch your email)

Teaching staff will add you to the GitHub Classroom roster manually and send invitations to your **university student email**.

You must accept:
1. The invitation to join the course GitHub organization (GitHub sends an email invitation).
2. The assignment invitation (GitHub Classroom link).

If you do not accept the invitations, you will not get your private assignment repository.

## 3) Join the classroom and link your roster identity (critical step)

When you open the assignment invitation link for the first time, GitHub Classroom will ask you to:
1. Authorize GitHub Classroom (click “Authorize GitHub”).
2. **Select your roster identifier** (your name/email as listed) and join the classroom.

Important:
- **Select your own roster entry only.**
- If you choose the wrong roster entry, your submissions may be graded under the wrong person.
- Because we roster manually and grade by roster identity, **you must use the correct GitHub account** when doing this.  [haagahelia.github.io](https://haagahelia.github.io/frontendprogramming/docs/general/github/)

## 4) Get your assignment repository and work normally

After accepting the assignment:
- GitHub Classroom creates a **private repository** for you in the course organization.
- Clone it locally, work, commit, and push.

Basic workflow:
1. Clone the repo:
   - `git clone <your-repo-url>`
2. Work only on the allowed parts (see below).
3. Commit and push:
   - `git add ...`
   - `git commit -m "message"`
   - `git push`

## 5) Strict rule: protected paths are not allowed to be modified

You are **not allowed** to modify any content under:

- `.github/**/*`
- `requirements.txt`
- `grader/**`
- `tests/**`
- `data/**`

These are protected grading and infrastructure files.

If you modify any of the above:
- it is detected automatically (GitHub Classroom flags “Protected file(s) modified” on your submission), and
- it results in **automatic disqualification** according to course policy.

GitHub Classroom supports “Protected file paths” and labels submissions that edited them.  [GitHub Docs](https://docs.github.com/en/education/manage-coursework-with-github-classroom/teach-with-github-classroom/create-an-individual-assignment)

Allowed area:
- You should only edit files under `student/**` unless explicitly stated otherwise in the assignment text.

## 6) Autograding and feedback

- Every push triggers the autograder (tests + training sanity checks).
- You will see pass/fail feedback in GitHub Classroom and in GitHub Actions for your repo.

## If something goes wrong

Common problems:
- You used the wrong GitHub account when accepting the assignment.
- You selected the wrong roster entry.
- You did not accept the GitHub organization invite email.

Fix:
- Contact teaching staff immediately.
- Do not try to “hack” it by creating new accounts or changing usernames.

## Discord dat560 Server Registration

1. Go to [Discord](https://discord.com/register) and register.
   A Discord account is required to sign in to communicate with the teaching staff during lab hours.
   You can skip this step if you already have an account.

2. To join our dat560-2026 Discord server, navigate [here](https://discord.gg/Wc6AqbAqE5).
3. Please use your legal name so that we know who you are. 

<!--
3. Once connected to the server, please register with our bot, `@dat560-help-bot`, by sending it a direct message:

   ```text
   !register username
   ```

   where `username` is your GitHub username.

   Note that to register with the bot, you must previously have registered with QuickFeed.
   Hence, please make sure that you have joined the [`dat560-2026`](https://github.com/dat560-2026) GitHub organization and registered with QuickFeed first.

   If you need help with registering on the server, send a message in `#new-users`.
-->

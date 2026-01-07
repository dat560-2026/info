# Signing up to DAT560 Generative AI

In this course we use **GitHub Classroom** for distributing assignments and collecting submissions.  
Your submission is your Git history on GitHub: you push commits, the autograder runs automatically.

In addition, you must **register your GitHub username in Canvas** before submitting assignments.

---

## 1) Create the right GitHub account (do this first if you dont have a GitHub account already)

1. Go to https://github.com and create a GitHub account (or use an existing one).
2. **Add your university student email address** to your GitHub account:
   - GitHub → Settings → Emails → Add email
   - Add your *student email address* and verify it.
3. Pick the GitHub account you will use for this course and **stick with it**.
   - **No switching accounts later**
   - **No username changes later**
   - This account must be used for **all submissions in this course**

Why so strict? GitHub Classroom permanently associates your GitHub account with your course submissions, and this account is used for grading and tracking throughout the course.  
[The GitHub Blog](https://github.blog/developer-skills/github-education/set-up-your-digital-classroom-with-github-classroom/)

### How to find your GitHub username (If you already have a GitHub account)

Your GitHub username is the name shown:
- at the top right of GitHub when you click your profile picture, and
- in your profile URL: https://github.com/
- Example:
   - If your profile URL is `https://github.com/octocat`
   - Your GitHub username is `octocat`
---


## 2) Register your GitHub username in Canvas (mandatory)

Before accepting any GitHub Classroom assignment, you must register your GitHub username in Canvas.

1. Go to Canvas and complete the **GitHub Username Registration** quiz [direct link](https://stavanger.instructure.com/courses/17651/quizzes/13006)
2. Enter **your GitHub username only**:
   - not your full name
   - not your email
   - not a URL
   - Like `octocat`
3. Submit the quiz/survey once.

Important:
- This information is visible **only to course staff**.
- The username you register must match the GitHub account you use for **all submissions**.
- Do **not** change your GitHub username after registering it.

Failure to register your GitHub username correctly may result in submissions not being graded.

---

## 3) Accept the course invitations (watch your email)

Teaching staff will invite students to GitHub Classroom.

You must accept:
1. The invitation to join the course GitHub organization (GitHub may send an email).
2. The assignment invitation via the GitHub Classroom link provided in Canvas.

If you do not accept the invitations, you will not get your private assignment repository.

---

## 4) Join the classroom and create your assignment repository

When you open a GitHub Classroom assignment link:

1. Authorize GitHub Classroom (first time only).
2. GitHub Classroom will create a **private assignment repository** for you in the course organization.
3. You will be redirected to your repository automatically.

You must use the **same GitHub account** that you registered in Canvas.

---

## 5) Work on assignments and submit

After accepting an assignment, GitHub Classroom creates a **private repository** for you in the course organization.

Basic workflow:

1. Clone your repository:
   ```
   git clone <your-repository-url>
   ```
2. Make changes **only** in the allowed areas.
3. Commit your work with a meaningful message:
   ```
   git add .
   git commit -m "Meaningful commit message"
   ```
4. Push your changes:
   ```
   git push
   ```

All submissions must be made from the **same GitHub account** that you registered in Canvas.

Each push triggers the autograder automatically.

## 6) Strict rule: protected paths are not allowed to be modified

You are **not allowed** to modify any content under:

- `.github/**/*`
- `requirements.txt`
- `grader/**`
- `tests/**`
- `data/**`

These files are part of the grading and infrastructure system.

If you modify any of the above:
- the change is detected automatically, and
- it results in **automatic disqualification** according to course policy.

GitHub Classroom monitors protected file paths and flags submissions that modify them.

Allowed area:
- You should only edit files under `student/**` unless explicitly stated otherwise in the assignment description.

---

## 7) Autograding and feedback

- Every push to your GitHub repository triggers the autograder automatically.
- The autograder runs public tests and additional hidden checks.
- Feedback is visible in:
  - GitHub Classroom, and
  - GitHub Actions in your assignment repository.
- Passing public tests does **not** guarantee full credit if hidden checks fail.
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

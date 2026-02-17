# GitHub Workout: A Hands-On Learning Plan

## Prerequisites

1. **Create a GitHub account** at github.com

2. **Install Git** on your machine (macOS):
   ```bash
   xcode-select --install
   ```
   Verify installation:
   ```bash
   git --version
   ```

3. **Configure Git** with your identity:
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your-email@example.com"
   ```

4. **Install Homebrew** (macOS package manager):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
   Then add it to your PATH:
   ```bash
   echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
   eval "$(/opt/homebrew/bin/brew shellenv)"
   ```

5. **Install GitHub CLI**:
   ```bash
   brew install gh
   ```

6. **Authenticate with GitHub**:
   ```bash
   gh auth login
   ```
   Select GitHub.com → HTTPS → Login with a web browser, then follow the prompts.

---

## Exercise: Build a "Workout Profile Card" Project

A simple project where learners create a workout profile card page — each workout teaches a core GitHub workflow.

---

### Step 1 — Create a Repository

- Go to GitHub → click **"New repository"**
- Name it `workout-profile-cards`
- Check **"Add a README"**
- Add a `.gitignore` (choose Node or any template)
- Pick a license (MIT is fine)
- Click **Create repository**

**Concepts learned:** repos, README, .gitignore, licenses

---

### Step 2 — Clone the Repo Locally

```bash
git clone https://github.com/<your-username>/workout-profile-cards.git
cd workout-profile-cards
```

**Concepts learned:** `git clone`, local vs remote

---

### Step 3 — Create Your First File on `main`

- Create `index.html` with a basic page skeleton
- Stage, commit, and push:

```bash
git add index.html
git commit -m "Add basic index.html skeleton"
git push origin main
```

**Concepts learned:** `git add`, `git commit`, `git push`, staging area

---

### Step 4 — Create a Feature Branch

```bash
git checkout -b add-profile-card
```

- Add a profile card `<div>` to `index.html` with your name, bio, and a fun fact
- Commit the change:

```bash
git add index.html
git commit -m "Add profile card for <your-name>"
```

**Concepts learned:** branching, `git checkout -b`, working on features in isolation

---

### Step 5 — Push the Branch & Open a Pull Request

```bash
git push origin add-profile-card
```

- Go to GitHub → you'll see a **"Compare & pull request"** banner
- Write a title and description explaining your change
- Click **Create pull request**

**Concepts learned:** pushing branches, PRs, code review workflow

---

### Step 6 — Review & Merge the PR

- On the PR page, look at the **Files changed** tab
- Leave a comment on your own PR (practice reviewing)
- Click **Merge pull request** → **Confirm merge**
- Delete the branch when prompted

**Concepts learned:** code review, merging, branch cleanup

---

### Step 7 — Pull the Merged Changes Locally

```bash
git checkout main
git pull origin main
```

**Concepts learned:** `git pull`, keeping local repo in sync

---

### Step 8 — Simulate a Merge Conflict

- Create two branches from `main`:

```bash
git checkout -b edit-card-v1
# Edit the bio line in index.html, commit & push

git checkout main
git checkout -b edit-card-v2
# Edit the SAME bio line differently, commit & push
```

- Open a PR for `edit-card-v1` and merge it
- Open a PR for `edit-card-v2` — GitHub will show a **conflict**
- Resolve it locally:

```bash
git checkout edit-card-v2
git merge main
# Fix the conflict markers in index.html
git add index.html
git commit -m "Resolve merge conflict"
git push origin edit-card-v2
```

**Concepts learned:** merge conflicts, conflict markers (`<<<<`, `====`, `>>>>`), resolution

---

### Step 9 — Use Issues for Task Tracking

- Go to the **Issues** tab → create an issue: *"Add a styles.css file for workout profile cards"*
- Assign it to yourself, add a label (e.g. `enhancement`)
- Create a branch, do the work, open a PR that says `Closes #1`
- Merge it — the issue auto-closes

**Concepts learned:** issues, labels, linking PRs to issues, auto-close keywords

---

### Step 10 — Collaborate (Fork & Contribute)

- Have a friend (or use a second account) **fork** the repo
- They clone their fork, add their own workout profile card on a branch
- They open a PR **from their fork** to your original repo
- You review and merge it

**Concepts learned:** forking, upstream vs origin, open-source contribution workflow

---

## Summary of Skills Covered

| Step | Skill |
|------|-------|
| 1 | Create a repo |
| 2 | Clone |
| 3 | Add, commit, push |
| 4 | Branching |
| 5 | Push branch, open PR |
| 6 | Review & merge PR |
| 7 | Pull changes |
| 8 | Merge conflicts |
| 9 | Issues & project tracking |
| 10 | Fork & contribute |

---

## Bonus Challenges

- **Enable GitHub Pages** to deploy the workout profile cards as a live website
- **Add a GitHub Action** that checks HTML validity on every PR
- **Protect the `main` branch** to require PR reviews before merging

#  Git Workflow Project - XYZ Corporation
> **A simple project to show how I used Git, CI/CD, and Auditing.**

---

##  1. Objective (Problem Statement)
My goal for this project was to create a clean and safe Git workflow for XYZ Corporation. I focused on:
* Handling **Merge Conflicts** when multiple people work together.
* Setting up **Continuous Integration (CI)** using GitHub Actions.
* Keeping the history clean with **Rebase and Squashing**.
* Tracking bugs and errors using **Git Blame**.

---

##  2. Tools Used & Solution Approach
I used these tools and methods to complete this assignment:
* **Git & Git Bash:** To manage the code and branches.
* **GitHub Actions:** To automate code checks (CI Pipeline).
* **Git Strategies:** Merging, Rebase, Squashing, and Stashing.
* **My Approach:** I manually created problems like bugs and conflicts in my own code, and then I showed how to fix them using Git.

---

##  3. Setup Instructions
If you want to run this project on your computer:
1. **Clone** this repository:  
   `git clone [My-Repo-Link]`
2. Make sure you have **Git Bash** installed.
3. Go to the project folder:  
   `cd devOps-Documentations/git-workflow`

---

##  4. What I Did (Task Summary & Execution)


#### **Task 1: Setting Up a Git Repository**
* **Scenario:** Starting a new project from scratch and setting up version control for the team.
* **What I did:** I initialized a new Git repository using the command `git init`. I created the first project file (`task1.txt`), staged it with `git add`, and made the **Initial Commit** to start the project history.
> !(screenshots/1.png)

---

#### **Task 2: Forking and Cloning a Project**
* **Scenario:** Contributing to an open-source project by creating a personal copy.
* **What I did:** I forked the `xyz-project` repository on GitHub to my account. Then, I used `git clone` to download the repository to my local machine for development.
> !(screenshots/2.4.png)

---

#### **Task 3: Branching Strategy (GitFlow)**
* **Scenario:** Following a branching strategy to work on new features without affecting the stable `main` branch.
* **What I did:** Following the **GitFlow** workflow, I created a new branch named `feature` using the command `git checkout -b feature`. I updated the `index.html` file with a login button and committed the changes to this specific branch.
> !(screenshots/3.1.png)

---

#### **Task 4: Collaboration and Pull Requests (PR)**
* **Scenario:** Sharing completed work with the team for code review and final merging.
* **What I did:** After finishing the feature, I used `git push origin feature` to upload my branch to GitHub and opened a **Pull Request (PR)** to merge my changes into the main repository.
> !(screenshots/4.2.png)

---

#### **Task 5: Handling Merge Conflicts**
* **Scenario:** While working on a feature branch, another teammate made conflicting changes in main. I need to handle the merge conflicts.
* **What I did:** I created a **Merge Conflict** on purpose by changing the same line in the `main` and `feature` branches. When Git failed to auto-merge, I manually opened the file, chose the correct code, and used `git add` and `git commit` to finalize the resolution.
> !(screenshots/5.1.png)
> !(screenshots/5.2.png)

---

#### **Task 6: Creating a Release and Tagging**
* **Scenario:** The application is stable and ready for its first official release. I need to create a version tag (v1.0).
* **What I did:** I used the command `git tag -a v1.0` to mark the current state of the project as Version 1.0. Then, I used `git push origin v1.0` to upload this tag to GitHub, making it a formal release.
> !(screenshots/6.1.png)
> !(screenshots/6.2.png)

---

#### **Task 7: Hotfix in Production**
* **Scenario:** After the official release, a critical bug was found in the production environment. The team needs an immediate fix.
* **What I did:** I created a dedicated branch `hotfix/urgent-bug-fix` to resolve the issue without disturbing the ongoing development. After fixing the bug and committing the changes, I merged the hotfix back into the `main` branch to ensure the production code is stable.
> !(screenshots/7.png)

---

#### **Task 8: Stashing Changes**
* **Scenario:** I was working on a new feature in the `dashboard-update` branch, but an urgent issue came up. I needed to switch branches immediately without losing or committing my half-finished work.
* **What I did:** I used the command `git stash save "Saving partial work for dashboard"`. This safely moved my uncommitted changes into a temporary "stash" area, making my working directory clean so I could switch branches without any errors.
> !(screenshots/8.png)

---

#### **Task 9: Cherry-Picking a Commit**
* **Scenario:** A specific commit from another branch contains a fix or a feature that I urgently need in my current branch, but I don't want to merge everything from that branch.
* **What I did:** I identified the commit hash (`6643067`) from the other branch and used the command `git cherry-pick 6643067`. Even though a conflict occurred, I resolved it manually and successfully applied only that specific change to my `dashboard-update` branch.
> !(screenshots/9.1.png)
> !(screenshots/9.3.png)

---

#### **Task 10: Integrating Continuous Integration (CI)**
* **Scenario:** The team wants to automate testing and code quality checks every time code is pushed to the `main` branch.
* **What I did:** I created a `.github/workflows/verify.yml` file to set up **GitHub Actions**. Even though I faced some initial challenges with "Personal Access Token" permissions and file conflicts, I successfully resolved them by pulling the latest changes and re-configuring the workflow.
* **Outcome:** Now, every push is automatically verified by GitHub.
> !(screenshots/10.2.png)
> !(screenshots/10.5.png)

---

#### **Task 11: Rebase vs Merge**
* **Scenario:** The team prefers a clean, linear commit history and wants to use `rebase` instead of `merge` to bring changes from the `main` branch into feature branches.
* **What I did:** I switched to my `login-feature` branch and used the command `git rebase main`. This moved my feature commits on top of the latest changes from the main branch. 
* **Outcome:** As shown in the `git log`, the history is now linear and clean, without the extra "merge commit" bubbles.
> !(screenshots/11.png)

---

#### **Task 12: Squashing Commits**
* **Scenario:** Before merging my feature branch, I need to simplify the history by combining multiple incremental commits into one.
* **What I did:** I used **Interactive Rebase** (`git rebase -i HEAD~3`) to view my last 3 commits. In the Vim editor, I kept the first commit as `pick` and changed the others to `s` (squash). 
* **Outcome:** I combined "basic setup", "fix login", and "style update" into one clean commit: *"feat: implement complete login module with styling"*. This keeps the project history clean and easy to read.
> !(screenshots/12.1.png)
> !(screenshots/12.2.png)

---

#### **Task 13: Git Blame for Debugging**
* **Scenario:** A bug was introduced in the codebase, and I need to identify which commit and author caused the issue.
* **What I did:** I simulated a security bug in `login.txt` (where access is allowed without a password). I then used the command `git blame login.txt` to audit the file. 
* **Outcome:** Git showed me exactly which user made the change, the date, and the specific commit hash (`d0e94ebb`). This is how professional teams track down and fix errors in large projects.
> !(screenshots/13.png)

---

## 📁 Folder Structure
* **`git workflow/`**: This has all my task files and logs.
* **`xyz-project/`**: The main project where I did the Rebase and Squash.
* **`screenshots/`**: This folder has all the proof for my tasks.

---

### ✅ Final Commands I Used:
```bash
git add .
git commit -m "docs: finalized readme with all 13 tasks and screenshots"
git push origin main --force
# 1TD076-Data-Engineering-2-Project

## Project Git Workflow

This document outlines the Git workflow used for this project. Following these steps ensures code consistency, facilitates review, and maintains stable `main` and `development` branches.

### Branches

* **`main`**: This branch represents the latest stable, production-ready code. Direct commits to `main` are forbidden. Merges into `main` typically come from `development` after thorough testing and represent official releases.
* **`development`**: This is the primary integration branch. All new features and bug fixes are merged into `development` via Pull Requests *after* approval. This branch contains the latest development changes but may not always be stable.
* **Feature Branches**: All new work (features, bug fixes, chores) MUST be done on separate branches, typically named using a convention like `feature/<feature-name>`, `bugfix/<bug-name>`, or `chore/<task-name>`. These branches are created *from* the `development` branch.

### Workflow Steps

1.  **Clone the Repository (First time only):**
    ```bash
    git clone git@github.com:alexandersundquist/1TD076-Data-Engineering-2-Project.git
    cd 1TD076-Data-Engineering-2-Project
    ```

2.  **Ensure `development` is Up-to-Date:** Before starting any new work, switch to the `development` branch and pull the latest changes:
    ```bash
    git checkout development
    git pull origin development
    ```

3.  **Create a New Feature Branch:** Create a new branch *from* the up-to-date `development` branch. Use a descriptive name.
    ```bash
    # Example: git checkout -b feature/user-authentication
    git checkout -b <branch-type>/<short-description>
    ```

4.  **Develop:** Make your code changes on your feature branch. Commit your work frequently with clear, concise commit messages.
    ```bash
    # Make changes...
    git add . # Or add specific files
    git commit -m "feat: Implement user login endpoint" # Example commit message
    ```
    *Tip: Write meaningful commit messages explaining *what* changed and *why*. Consider using [Conventional Commits](https://www.conventionalcommits.org/) if desired.*

5.  **Keep Your Branch Updated (Optional but Recommended):** Periodically update your feature branch with the latest changes from `development` to minimize large merge conflicts later.
    ```bash
    git fetch origin development
    git merge origin/development # This merges the latest development changes into your feature branch
    # Resolve any merge conflicts if they occur, then commit the merge
    git commit -m "Merge branch 'development' into <your-branch-name>"
    ```
    *(Alternatively, use `git rebase origin/development` if you prefer a linear history, but be cautious with rebasing branches that are already pushed and shared).*

6.  **Push Your Feature Branch:** Once your feature is complete or ready for feedback, push it to the remote repository:
    ```bash
    git push -u origin <your-branch-name> # Use -u on the first push to set the upstream
    ```

7.  **Create a Pull Request (PR):**
    * Go to the repository page on GitHub/GitLab/Bitbucket.
    * You should see a prompt to create a Pull Request for your recently pushed branch. Click it.
    * Ensure the **base branch** is `development` and the **compare branch** is your feature branch (`<your-branch-name>`).
    * Write a clear title and detailed description for your PR. Explain the changes made, the reason for them, and how to test them. Link to any relevant issues.

8.  **Code Review and Approval:**
    * Your PR will be reviewed.
    * **IMPORTANT:** Only the designated project lead can approve and merge Pull Requests into the `development` branch.
    * Address any feedback by making changes locally on your feature branch, committing them, and pushing again to the *same* branch. The PR will update automatically.

9.  **Merging:** Once the PR is approved, the project lead will merge it into the `development` branch.

10. **Cleanup:** After your PR is successfully merged into `development`, you can clean up your local and remote branches:
    ```bash
    # Switch back to development and pull the merged changes
    git checkout development
    git pull origin development

    # Delete the local feature branch
    git branch -d <your-branch-name>

    # Delete the remote feature branch (optional, can also be done via the web UI)
    git push origin --delete <your-branch-name>
    ```

### Summary

* Always branch from `development`.
* Do work in dedicated feature/bugfix branches.
* Merge back into `development` via Pull Requests.
* Keep `main` stable and only merge tested `development` code into it for releases.

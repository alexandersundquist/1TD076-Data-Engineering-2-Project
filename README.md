# 1TD076-Data-Engineering-2-Project

## Git Workflow Instructions

Welcome to our project! Follow these instructions to set up your environment and start contributing.

### 1. **Clone the Repository**
Begin by cloning the repository to your local machine. Replace `URL` with the actual URL of the repository:
```bash
git clone URL
cd [repository-name]
```

### 2. **Set Up Your Local Environment**
Switch to the development branch to pull the latest changes and prepare to branch off:
```bash
git checkout development
git pull
```

### 3. **Create Your Own Branch**
Create a new branch for your work. Name your branch in a way that reflects the feature or issue you're addressing:
```bash
git checkout -b feature/your-branch-name
```
Replace `feature/your-branch-name` with a suitable name for your branch.

### 4. **Make Changes**
Perform your work on this branch. Remember to keep your changes focused and related to the task at hand.

### 5. **Commit Your Changes**
After making changes, add them to your branch and commit them with a clear, descriptive message:
```bash
git add .
git commit -m "A descriptive message about the change"
```

### 6. **Push Changes to Your Branch**
Once you have a meaningful set of changes committed, push your branch to the remote repository:
```bash
git push -u origin feature/your-branch-name
```

### 7. **Prepare to Merge to Development**
After you have tested your changes and are satisfied with the work on your branch, merge the latest changes from the development branch and resolve any conflicts:
```bash
git checkout development
git pull
git checkout feature/your-branch-name
git merge development
# Resolve any conflicts if they exist
```

### 8. **Push to Development**
Once conflicts are resolved and your feature is ready, push your branch again (if new commits were made) and then switch to the development branch to merge your changes:
```bash
git push
git checkout development
git merge feature/your-branch-name
git push
```

### 9. **Clean Up**
After your changes have been successfully merged into the development branch, you can delete your local feature branch if desired:
```bash
git branch -d feature/your-branch-name
```
Optionally, delete the remote branch if it is no longer needed:
```bash
git push origin --delete feature/your-branch-name
```

### 10. **Stay Updated**
Regularly update your development branch to stay in sync with the main repository:
```bash
git checkout development
git pull
```

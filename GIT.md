# Git Documentation

## Introduction

This document provides an overview of Git, including installation instructions, basic commands, and common branching strategies used in software development projects(Add more details and images if you can).

**Git** is a tool used to track file changes, especially when multiple people are working on a project. It is a **version control system**, which means it helps you manage different versions of your files and makes it easier to work on a project as a team. 

### Why Git is used in software development projects:
1. **Track Changes**: Git keeps a history of all file changes, so you can see what has been modified and when.
2. **Collaboration**: Multiple people can work on the same project without overwriting each other's work. Git helps merge their changes.
3. **Error Recovery**: If you make a mistake, you can return to your work's earlier version.
4. **Branching and Merging**: You can create separate branches (copies) of a project to try new ideas or features without affecting the main project. Once everything is ready, you can combine the changes back.
5. **Transparency**: It shows who made what changes, making it easier to understand the progress and contributions of team members.

Git is popular in software development because it is fast, reliable, and helps teams work together effectively.


## Installing Git


### For Windows OS
1. Visit the official Git website at [https://git-scm.com/download/win](https://git-scm.com/download/win).  
   The download should begin automatically. If it doesn't, click on the appropriate link for your system (32-bit or 64-bit).

2. Launch the downloaded installer and follow the instructions provided.

3. Select the default options or modify the installation settings based on your preferences.

4. Once the installation is complete, open Command Prompt and confirm the installation by entering:  
   `git --version`.

### For macOS:
  1. **Install using Homebrew**: If you already have Homebrew installed, run the following command:  
   `brew install git`.

2. **If Homebrew is not installed**: To install Homebrew, open Terminal and run the following command:  
   ```
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
   Once Homebrew is installed, proceed with the command:  
   `brew install git`.

3. **Alternative method**: If you prefer, download the `.dmg` installer from [Git's official website](https://git-scm.com/) and follow the on-screen instructions.

4. **Verify the installation**: After the installation is complete, open Terminal and check the Git version by typing:  
   `git --version`.



### For Linux OS:
For Ubuntu/Debian:  
```bash
sudo apt-get update
sudo apt-get install git
```

For Fedora:  
```bash
sudo dnf install git
```

**Verify the installation**:  
After installation, open the terminal and check the Git version by running:  
```bash
git --version
```

## Configuring Git

Once Git is installed, it's essential to configure it with your username and email address. This information will be associated with your commits and helps identify you as the author of the changes.

### Basic Configuration Commands

To set your username and email globally (for all repositories on your system), use the following commands:

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

### Setting Configuration for a Specific Repository

If you want to set a username and email for just a single repository, navigate to the repository directory and run:

```bash
git config user.name "Your Name"
git config user.email "your_email@example.com"
```

### Verifying the Configuration
You can verify the configuration using this command:

```bash
git config --global --list
```
This will display the currently configured username, email, and other global Git settings.

### Example Output
After running the configuration commands, the output of git config --global --list might look like this:

```bash
user.name=John Doe
user.email=johndoe@example.com
```
## Using Git - Basic Commands

The following are some of the basic Git commands used to manage repositories, track changes, and collaborate with other developers, complete them with the appropriate commands:

### 1. Initializing a Repository

To start tracking changes in a project, navigate to the project directory and run:

```bash
git init
```

### 2. Cloning a Repository

To clone an existing repository, use the following command:

```bash
git clone <repository_url>
```

### 3. Staging Changes

Before committing changes, you need to stage them. Use the following command to stage changes:

```bash
git add <file_name>
git add 
```

### 4. Committing Changes

Committing staged changes to the repository:

```bash
git commit -m "Your commit message"
```

### 5. Checking Status

Check the status of your working directory:

```bash
git status
```

### 6. Viewing Commit History

View the commit history of the repository:

```bash
git log
```
## Other git commands
---

#### **1. `git pull`**
- **Description:** Fetches updates from the remote repository and merges them into your current branch. Keeps your local repository in sync with others.
- **Example:**
  ```bash
  git pull origin main
  ```
- **Scenario:** Your teammates pushed new changes to the `main` branch, and you want to update your local `main` branch with their work.

---

#### **2. `git push`**
- **Description:** Uploads local changes to the remote repository, sharing your updates with collaborators.
- **Example:**
  ```bash
  git push origin feature-branch
  ```
- **Scenario:** You've finished working on a feature branch and want to make it available for code review.

---

#### **3. `git branch`**
- **Description:** Lists, creates, or deletes branches to manage separate lines of development.
- **Example:**
  ```bash
  git branch feature-login
  ```
- **Scenario:** You’re starting work on a new feature and want to isolate changes in a dedicated branch.

---

#### **4. `git checkout`**
- **Description:** Switches to another branch or restores a specific commit.
- **Example:**
  ```bash
  git checkout main
  git checkout a1b2c3d
  ```
- **Scenario:** Switch to the `main` branch to test the latest stable code or check the state of the project at a past commit.

---

#### **5. `git merge`**
- **Description:** Combines changes from one branch into the current branch.
- **Example:**
  ```bash
  git merge feature-login
  ```
- **Scenario:** Your `feature-login` branch is complete, and you want to integrate it into the `main` branch.

---

#### **6. `git rebase`**
- **Description:** Reapplies commits from one branch onto another, creating a linear history.
- **Example:**
  ```bash
  git checkout feature-login
  git rebase main
  ```
- **Scenario:** Sync your `feature-login` branch with the latest changes from the `main` branch without introducing a merge commit.

---

#### **7. `git log`**
- **Description:** Displays the commit history with details like author, date, and changes.
- **Example:**
  ```bash
  git log --oneline --graph
  ```
- **Scenario:** Review the commit history to understand changes made by the team.

---

#### **8. `git reset`**
- **Description:** Resets the repository to a previous state, undoing changes.
- **Example:**
  ```bash
  git reset --soft HEAD~1  # Undo last commit but keep changes staged
  git reset --hard HEAD~1  # Undo last commit and discard changes
  ```
- **Scenario:** Fix a mistake in the last commit or remove unwanted changes completely.

---

#### **9. `git tag`**
- **Description:** Marks specific commits with labels for significant milestones or releases.
- **Example:**
  ```bash
  git tag -a v1.0 -m "Version 1.0 Release"
  git push origin v1.0
  ```
- **Scenario:** Label the commit representing your first stable release.

---

#### **10. `git stash`**
- **Description:** Temporarily saves uncommitted changes to switch contexts.
- **Example:**
  ```bash
  git stash
  git checkout main
  git stash pop
  ```
- **Scenario:** Save incomplete work on a feature to fix a bug on another branch.

---

#### **11. `git fetch`**
- **Description:** Downloads changes from the remote repository without merging them into your branch.
- **Example:**
  ```bash
  git fetch origin
  ```
- **Scenario:** Check for updates on the remote repository without affecting your working branch.

---

#### **12. `git remote`**
- **Description:** Manages remote repository connections.
- **Example:**
  ```bash
  git remote add origin https://github.com/user/repo.git
  git remote -v
  ```
- **Scenario:** Add a new remote repository or verify existing remotes.

---

#### **13. `git diff`**
- **Description:** Shows differences between commits, branches, or the working directory.
- **Example:**
  ```bash
  git diff main feature-branch
  git diff HEAD
  ```
- **Scenario:** Compare changes in your working directory with the last commit or between branches.

---

#### **14. `git blame`**
- **Description:** Displays the last modification for each line in a file.
- **Example:**
  ```bash
  git blame app.js
  ```
- **Scenario:** Identify who last modified a specific line of code for debugging or accountability.

---

#### **15. `git cherry-pick`**
- **Description:** Applies a specific commit from one branch to another.
- **Example:**
  ```bash
  git cherry-pick a1b2c3d
  ```
- **Scenario:** Integrate a bug fix from one branch into another without merging unrelated changes.



Define the branching strategies used in your project, such as feature branching, release branching, or GitFlow. Explain how branches are created, merged, and deleted in your workflow, Give examples of common branching commands.

### 1. Creating a Branch



```bash
git branch <branch_name>
```

Alternatively, you can combine these commands using:

```bash
git checkout -b <branch_name>
```

### 2. Merging Branches



```bash
git merge <branch_name>
```

### 3. Resolving Conflicts



```bash
git add <resolved_file>
git commit
```

### 4. Deleting a Branch



```bash
git branch -d <branch_name>
```

## VERSION CONTROL
### Comparison of Version Control Systems  

#### 1. **Centralized Version Control System (CVCS)**  
- **Definition**: Relies on a single central server to store all versioned files. Users must connect to this server to retrieve or update files.  
- **Examples**: Subversion (SVN), Perforce.  
- **Advantages**:  
  - Simpler to manage with a single repository.  
  - Easy to understand and use for small teams.  
- **Disadvantages**:  
  - Server failure leads to downtime.  
  - Requires constant internet access for most operations.  

#### 2. **Distributed Version Control System (DVCS)**  
- **Definition**: Every user has a complete copy of the repository, including history, allowing offline work and decentralization.  
- **Examples**: Git, Mercurial.  
- **Advantages**:  
  - Full offline capabilities for all operations.  
  - No single point of failure, making it more resilient.  
  - Faster operations since many tasks are local.  
- **Disadvantages**:  
  - More complex for beginners.  
  - Requires more storage as every user maintains a full repository copy.  

#### 3. **Local Version Control System (LVCS)**  
- **Definition**: Tracks file changes only on a local machine, without collaboration or centralized control.  
- **Examples**: RCS (Revision Control System), SCCS (Source Code Control System).  
- **Advantages**:  
  - Simple and lightweight.  
  - Does not depend on a network or server.  
- **Disadvantages**:  
  - Lacks collaboration capabilities.  
  - Cannot manage shared repositories across multiple users.  

### Key Differences  
- CVCS is centralized and requires a server, suitable for small teams with limited collaboration needs.  
- DVCS supports decentralized workflows, offline operations, and enhanced collaboration, making it ideal for modern development teams.  
- LVCS is limited to individual use and is outdated for most current development practices.  

# Table of Contents

- [What is Git?](#what-is-git)
  - [Key Git Concepts](#key-git-concepts)
  - [Working with Git](#working-with-git)
- [Git Install](#git-install)
  - [How to Install Git](#how-to-install-git)
  - [Git Bash](#git-bash)
  - [Verifying Your Installation](#verifying-your-installation)
  - [Default Editor](#default-editor)
  - [PATH Environment](#path-environment)
  - [Line Endings](#line-endings)
  - [Updating or Uninstalling Git](#updating-or-uninstalling-git)
  - [Troubleshooting Git Installation](#troubleshooting-git-installation)
- [Git Config](#git-config)
  - [Configure Git](#configure-git)
  - [Viewing Your Configuration](#viewing-your-configuration)
  - [Changing or Unsetting Config Values](#changing-or-unsetting-config-values)
  - [Default Branch Name](#default-branch-name)
  - [Configuration Levels](#configuration-levels)
- [Git Getting Started](#git-getting-started)
  - [Get Started with Git](#get-started-with-git)
  - [Creating Git Folder](#creating-git-folder)
  - [Initialize Git](#initialize-git)
  - [Troubleshooting](#troubleshooting)
- [Git New Files](#git-new-files)
  - [What is a New File?](#what-is-a-new-file)
  - [Create a New File](#create-a-new-file)
  - [List Files in the Directory](#list-files-in-the-directory)
  - [Check File Status with `git status`](#check-file-status-with-git-status)
  - [Troubleshooting](#troubleshooting-1)
- [Git Staging Environment](#git-staging-environment)
  - [What is the Staging Environment?](#what-is-the-staging-environment)
  - [Stage a File with `git add`](#stage-a-file-with-git-add)
  - [Stage Multiple Files (`git add --all`, `git add -A`)](#stage-multiple-files-git-add---all-git-add--a)
  - [How to Unstage a File](#how-to-unstage-a-file)
  - [Troubleshooting](#troubleshooting-2)
- [Git Commit](#git-commit)
  - [What is a Commit?](#what-is-a-commit)
  - [How to Commit with a Message (`-m`)](#how-to-commit-with-a-message--m)
  - [Commit All Changes Without Staging (`-a`)](#commit-all-changes-without-staging--a)
  - [Write Multi-line Commit Messages](#write-multi-line-commit-messages)
  - [Other Useful Commit Options](#other-useful-commit-options)
  - [Troubleshooting Common Commit Mistakes](#troubleshooting-common-commit-mistakes)
  - [View Commit History (`git log`)](#view-commit-history-git-log)
- [Git Tagging](#git-tagging)
  - [Key Commands for Tagging](#key-commands-for-tagging)
  - [What is a Tag?](#what-is-a-tag)
  - [Create a Lightweight Tag](#create-a-lightweight-tag)
  - [Create an Annotated Tag (`-a -m`)](#create-an-annotated-tag--a--m)
  - [Tag a Specific Commit](#tag-a-specific-commit)
  - [List Tags](#list-tags)
  - [Show Tag Details (`git show`)](#show-tag-details-git-show)
  - [Push Tags to Remote](#push-tags-to-remote)
  - [Delete Tags](#delete-tags)
  - [Update or Replace a Tag (Force Push)](#update-or-replace-a-tag-force-push)
  - [Tagging Best Practices](#tagging-best-practices)
  - [Troubleshooting](#troubleshooting-3)
- [Git Stash](#git-stash)
  - [Key Commands for Stashing](#key-commands-for-stashing)
  - [What is Git Stash? Why Use It?](#what-is-git-stash-why-use-it)
  - [Stash Your Changes (`git stash`)](#stash-your-changes-git-stash)
  - [Stash with a Message (`git stash push -m`)](#stash-with-a-message-git-stash-push--m)
  - [List All Stashes (`git stash list`)](#list-all-stashes-git-stash-list)
  - [Show Stash Details (`git stash show`)](#show-stash-details-git-stash-show)
  - [Apply the Latest Stash (`git stash apply`)](#apply-the-latest-stash-git-stash-apply)
  - [Apply a Specific Stash (`git stash apply stash@{n}`)](#apply-a-specific-stash-git-stash-apply-stashn)
  - [Pop the Stash (`git stash pop`)](#pop-the-stash-git-stash-pop)
  - [Drop a Stash (`git stash drop`)](#drop-a-stash-git-stash-drop)
  - [Clear All Stashes (`git stash clear`)](#clear-all-stashes-git-stash-clear)
  - [Branch from a Stash (`git stash branch`)](#branch-from-a-stash-git-stash-branch)
  - [Best Practices for Stashing](#best-practices-for-stashing)
  - [Troubleshooting](#troubleshooting-4)
- [Git History](#git-history)
  - [What is Git History? Why Use It?](#what-is-git-history-why-use-it)
  - [Best Practices for Viewing History](#best-practices-for-viewing-history)
  - [See Commit History (`git log`)](#see-commit-history-git-log)
  - [Show Commit Details (`git show <commit>`)](#show-commit-details-git-show-commit)
  - [Compare Changes (`git diff`)](#compare-changes-git-diff)
  - [Compare Staged Changes (`git diff --staged`)](#compare-staged-changes-git-diff---staged)
  - [Compare Two Commits (`git diff <commit1> <commit2>`)](#compare-two-commits-git-diff-commit1-commit2)
  - [Show a Summary of Commits (`git log --oneline`)](#show-a-summary-of-commits-git-log---oneline)
  - [Show Commits by Author (`git log --author="Alice"`)](#show-commits-by-author-git-log---authoralice)
  - [Show Recent Commits (`git log --since="2 weeks ago"`)](#show-recent-commits-git-log---since2-weeks-ago)
  - [Show Files Changed Per Commit (`git log --stat`)](#show-files-changed-per-commit-git-log---stat)
  - [Show a Branch Graph (`git log --graph`)](#show-a-branch-graph-git-log---graph)
  - [Troubleshooting](#troubleshooting-5)
- [Git Help](#git-help)
  - [Why and When to Use Git Help?](#why-and-when-to-use-git-help)
  - [See Help for a Specific Command (`git help <command>`)](#see-help-for-a-specific-command-git-help-command)
  - [See Help with `--help` (`git <command> --help`)](#see-help-with---help-git-command---help)
  - [See a Quick Summary with `-h` (`git <command> -h`)](#see-a-quick-summary-with--h-git-command--h)
  - [List All Git Commands (`git help --all`)](#list-all-git-commands-git-help---all)
  - [List Guides and Concepts (`git help -g`)](#list-guides-and-concepts-git-help--g)
  - [Troubleshooting](#troubleshooting-6)
- [Git Branch](#git-branch)
  - [What is a Git Branch?](#what-is-a-git-branch)
  - [Creating a New Branch](#creating-a-new-branch)
  - [Listing All Branches](#listing-all-branches)
  - [Switching Between Branches](#switching-between-branches)
  - [Working in a Branch](#working-in-a-branch)
  - [Emergency Branch](#emergency-branch)
  - [Deleting a Branch](#deleting-a-branch)
  - [Best Practices for Working with Branches](#best-practices-for-working-with-branches)
  - [Practical Examples](#practical-examples)
  - [Troubleshooting](#troubleshooting-7)
- [Git Branch Merge](#git-branch-merge)
  - [What is Merging in Git?](#what-is-merging-in-git)
  - [Merging Branches (`git merge`)](#merging-branches-git-merge)
  - [Non-Fast-Forward Merge (`git merge --no-ff`)](#non-fast-forward-merge-git-merge---no-ff)
  - [Squash Merge (`git merge --squash`)](#squash-merge-git-merge---squash)
  - [Aborting a Merge (`git merge --abort`)](#aborting-a-merge-git-merge---abort)
  - [What is a Merge Conflict?](#what-is-a-merge-conflict)
  - [Merge Conflict Example](#merge-conflict-example)
  - [Best Practices for Merging Branches](#best-practices-for-merging-branches)
  - [Practical Examples](#practical-examples-1)
  - [Troubleshooting & Tips](#troubleshooting--tips)
- [Git Workflow](#git-workflow)
  - [Git Workflow Commands Overview](#git-workflow-commands-overview)
  - [Understanding the Git Workflow](#understanding-the-git-workflow)
  - [Working Directory](#working-directory)
  - [Staging Changes (`git add`)](#staging-changes-git-add)
  - [Committing Changes (`git commit`)](#committing-changes-git-commit)
  - [Pushing Changes (`git push`)](#pushing-changes-git-push)
  - [Checking Status (`git status`)](#checking-status-git-status)
  - [Undoing and Amending Changes](#undoing-and-amending-changes)
  - [Best Practices for Git Workflow](#best-practices-for-git-workflow)
  - [Tips & Troubleshooting](#tips--troubleshooting)

---

# What is Git?

Git is a popular version control system.

It was created by Linus Torvalds in 2005, and has been maintained by Junio Hamano since then.

It is used for:
* Tracking code changes
* Tracking who made changes
* Coding collaboration

## Key Git Concepts

* **Repository**: A folder where Git tracks your project and its history.
* **Clone**: Make a copy of a remote repository on your computer.
* **Stage**: Tell Git which changes you want to save next.
* **Commit**: Save a snapshot of your staged changes.
* **Branch**: Work on different versions or features at the same time.
* **Merge**: Combine changes from different branches.
* **Pull**: Get the latest changes from a remote repository.
* **Push**: Send your changes to a remote repository.

## Working with Git

1. Initialize Git on a folder, making it a Repository.
2. Git now creates a hidden folder to keep track of changes in that folder.
3. When a file is changed, added or deleted, it is considered modified.
4. You select the modified files you want to Stage.
5. The Staged files are Committed, which prompts Git to store a permanent snapshot of the files.

* Git allows you to see the full history of every commit.
* You can revert back to any previous commit.
* Git does not store a separate copy of every file in every commit, but keeps track of changes made in each commit!

### Summary of Concepts & Actions

| Concept / Action | Description |
| :--- | :--- |
| **Initialize** | Initialize Git on a folder, making it a Repository |
| **Clone** | Make a copy of a remote repository on your computer |
| **Stage** | Tell Git which changes you want to save next |
| **Commit** | Save a snapshot of your staged changes / store a permanent snapshot of the files |
| **Branch** | Work on different versions or features at the same time |
| **Merge** | Combine changes from different branches |
| **Pull** | Get the latest changes from a remote repository |
| **Push** | Send your changes to a remote repository |

---

# Git Install

## How to Install Git

You can download Git for free from [git-scm.com](https://git-scm.com).

* **Windows**: Download and run the installer. Click "Next" to accept the recommended settings. This will install Git and Git Bash.
* **macOS**: If you use Homebrew, open Terminal and type:
  ```bash
  brew install git
  ```
  Or, download the `.dmg` file and drag Git to your Applications folder.
* **Linux**: Open your terminal and use your package manager. For example, on Ubuntu:
  ```bash
  sudo apt-get install git
  ```

After installation, you will be able to use Git from your terminal or command prompt.

> [!TIP]
> **Tip for Beginners:** Installing Git is safe and you can always uninstall it later if you want.

## Git Bash

Git Bash is a terminal for Windows that lets you use Git commands.

Look at our Bash Tutorial to learn more about Bash.

After installing Git, you can find Git Bash in your Start menu.

You can use Git Bash just like the Command Prompt, but with extra Unix commands (like `ls` and `pwd`).

### Example: Open Git Bash
Click Start, type "Git Bash", and open the app.

### Example: First Command in Git Bash
```bash
ls
```
**Output:**
```text
Desktop  Documents  Downloads  Pictures
```
This command lists the files in your current folder.

## Verifying Your Installation

After installing, check that Git works by opening your terminal (or Git Bash on Windows) and running:

### Example: Check Git Version
```bash
git --version
```
**Output:**
```text
git version 2.43.0.windows.1
```
If Git is installed, you will see something like `git version X.Y.Z`.

If you see an error, try closing and reopening your terminal, or check that Git is in your PATH.

## Default Editor

During installation, Git asks you to pick a default text editor.

This is the program that will open when you need to write messages (like for commits).

### Example: Set VS Code as Default Editor
```bash
git config --global core.editor "code --wait"
```
If you're not sure, just pick the default (Notepad on Windows). You can always change this later.

### Example: Set Notepad as Default Editor
```bash
git config --global core.editor "notepad"
```

## PATH Environment

Choosing to add Git to your PATH means you can use Git commands in any terminal window.

This is highly recommended for most users to do this during installation.

If you skip this, you'll only be able to use Git in Git Bash (on Windows) or Terminal (on macOS and Linux).

### Example: Check if Git is in PATH
```bash
git --version
```
**Output:**
```text
git version 2.43.0.windows.1
```
If you see an error, you need to add Git to your PATH.

### How to Add Git to PATH after Installation

#### Windows
1. If you missed the option during installation, search for "Environment Variables" in the Start menu and open it.
2. Click "Environment Variables..." and find the "Path" variable under "System variables".
3. Click "Edit", then "New", and add the path to your Git `bin` and `cmd` folders (e.g., `C:\Program Files\Git\bin` and `C:\Program Files\Git\cmd`).
4. Click OK to save. Restart your terminal.

#### macOS
1. If you installed with Homebrew, your PATH is usually set automatically.
2. If not, open Terminal and add this line to your `~/.zshrc` or `~/.bash_profile`:
   ```bash
   export PATH="/usr/local/bin:$PATH"
   ```
3. Save the file and run `source ~/.zshrc` or `source ~/.bash_profile`.

#### Linux
1. Most package managers add Git to PATH automatically.
2. If not, add this line to your `~/.bashrc` or `~/.profile`:
   ```bash
   export PATH="/usr/bin:$PATH"
   ```
3. Save the file and run `source ~/.bashrc` or `source ~/.profile`.

After adding Git to your PATH, open a new terminal window and run `git --version` to check that it works everywhere.

## Line Endings

Git can convert line endings in text files.

On Windows, it's usually best to select "Checkout Windows-style, commit Unix-style line endings".

This helps prevent problems when you share code with people using different operating systems.

## Updating or Uninstalling Git

* **Update**: Download and run the latest installer, or use your package manager:
  ```bash
  brew upgrade git
  # or
  sudo apt-get upgrade git
  ```
  It's a good idea to keep Git up to date for the latest features and security fixes.
* **Uninstall**: Use "Add or Remove Programs" on Windows, or your package manager on Mac/Linux.

## Troubleshooting Git Installation

If you run into problems installing or running Git, don't worry!

Here are solutions to some of the most common issues.

> [!TIP]
> **Tip:** If something doesn't work right away, try closing and reopening your terminal, or restarting your computer.

### Common Installation Issues

* **"git is not recognized as an internal or external command"**
  * **Solution:** Git is not in your system's PATH. Make sure you installed Git and restart your terminal. If needed, add Git's bin folder (usually `C:\Program Files\Git\bin`) to your PATH. If it still doesn't work, try restarting your computer.
* **Permission errors ("Permission denied")**
  * **Solution:** On Windows, run Git Bash or your terminal as administrator. On macOS/Linux, use `sudo` if necessary.
* **SSL or HTTPS errors when cloning/pushing**
  * **Solution:** Check your internet connection. Make sure your Git version is up to date.
* **Wrong version of Git**
  * **Solution:** Check your installed version with `git --version`. Download the latest version from [git-scm.com](https://git-scm.com) if needed.

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `brew install git` | Install Git on macOS using Homebrew |
| `sudo apt-get install git` | Install Git on Ubuntu/Linux using the package manager |
| `ls` | Lists the files in your current folder |
| `pwd` | Check your current directory |
| `git --version` | Check the installed Git version to verify installation/PATH |
| `git config --global core.editor "code --wait"` | Set VS Code as the default Git text editor |
| `git config --global core.editor "notepad"` | Set Notepad as the default Git text editor |
| `export PATH="/usr/local/bin:$PATH"` | Add Git path to PATH environment variable on macOS |
| `source ~/.zshrc` / `source ~/.bash_profile` | Apply and reload PATH configuration changes on macOS |
| `export PATH="/usr/bin:$PATH"` | Add Git path to PATH environment variable on Linux |
| `source ~/.bashrc` / `source ~/.profile` | Apply and reload PATH configuration changes on Linux |
| `brew upgrade git` | Upgrade Git to the latest version on macOS using Homebrew |
| `sudo apt-get upgrade git` | Upgrade Git to the latest version on Linux using the package manager |

---

# Git Config

## Configure Git

Now let Git know who you are.

This is important for version control systems, as each Git commit uses this information:

> [!TIP]
> **Tip for Beginners:** Configuring Git is safe. You can change these settings at any time, they only affect how your name and email appear in your commits.

### User Name

Your name will be attached to your commits. Set it with:

#### Example
```bash
git config --global user.name "Your Name"
```

> [!NOTE]
> **Note:** If you make a typo or mistake, just run the command again with the correct value. The new setting will overwrite the old one.

### Email Address

Your email is also attached to your commits. Set it with:

#### Example
```bash
git config --global user.email "you@example.com"
```

Change the user name and email to your own. You will probably also want to use this when registering to GitHub later on.

> [!NOTE]
> **Note:** If you forget to set your name or email, Git will prompt you the first time you try to commit. You can always change these settings later, and previous commits will keep the old info.

* Use `--global` to set the value for every repository on your computer.
* Use `--local` (the default) to set it only for the current repository.

### Why Configure Git?

Git uses your name and email to label your commits. If you do not set these, Git will prompt you the first time you try to commit.

Now you have added the minimum of configuration needed to start using Git. So feel free to continue with the next chapter.

For more information about configuration, or if you want to change anything, keep reading this page.

## Viewing Your Configuration

You can see all your Git settings with:

### Example: List All Settings
```bash
git config --list
```
**Output:**
```text
user.name=Your Name
user.email=you@example.com
core.editor=code --wait
alias.st=status
init.defaultbranch=main
...
```

To view a specific value, use:

### Example: View a Specific Setting
```bash
git config user.name
```
**Output:**
```text
Your Name
```

## Changing or Unsetting Config Values

To change a value, just run the `git config` command again with the new value.

To remove a setting, use `--unset`:

### Example: Unset an Alias
```bash
git config --global --unset code.editor
```

## Default Branch Name

Set the default branch name for new repositories (for example, `main` instead of `master`):

### Example: Set Default Branch Name
```bash
git config --global init.defaultBranch main
```

## Configuration Levels

There are three levels of configuration:
* **System** (all users): `git config --system`
* **Global** (current user): `git config --global`
* **Local** (current repo): `git config --local`

The order of precedence is:
1. Local (current repo)
2. Global (current user)
3. System (all users)

The reason to use the different levels is that you can set different values for different users or repositories. This can be used for example to set different default branches for different repositories and users.

### Example: Set a Local Config
Local settings only apply to the current repository.
```bash
git config user.name "Project Name"
```

### Example: Set a Global Config
Global settings apply to all repositories for the current user.
```bash
git config --global user.name "Global Name"
```

### Example: Set a System Config
System settings apply to all repositories for all users.
```bash
git config --system user.name "System Name"
```

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `git config --global user.name "Your Name"` | Set global user name for your commits |
| `git config --global user.email "you@example.com"` | Set global email address for your commits |
| `git config --list` | List all Git configuration settings |
| `git config user.name` | View the specific `user.name` configuration value |
| `git config --global --unset code.editor` | Unset a global configuration variable (e.g., `code.editor`) |
| `git config --global init.defaultBranch main` | Set the default branch name to `main` for new repositories |
| `git config --system` | Access system-level configuration (applies to all users on the machine) |
| `git config --global` | Access global-level configuration (applies to current system user) |
| `git config --local` | Access local-level configuration (applies to current repository only) |
| `git config user.name "Project Name"` | Set a local configuration value for `user.name` |
| `git config --global user.name "Global Name"` | Set a global configuration value for `user.name` |
| `git config --system user.name "System Name"` | Set a system configuration value for `user.name` |

---

# Git Getting Started

## Get Started with Git

Now that Git is installed, and it knows who you are, you can start using Git.

Let's create our first repository.

### Key Steps to Get Started
1. Create a project folder
2. Navigate to the folder
3. Initialize a Git repository

## Creating Git Folder

Start by creating a new folder for our project:

### Example
```bash
mkdir myproject
cd myproject
```

* `mkdir` creates a new directory.
* `cd` changes our working directory.

Now we are in the correct directory and can initialize Git!

> [!NOTE]
> **Note: Open Git Bash Here (Windows)**
> If you're using Windows, you can open Git Bash directly in your project folder:
> 1. Right-click the folder in File Explorer.
> 2. Select **Git Bash Here**.
> 
> This opens a terminal window in the correct location.

## Initialize Git

Now that we are in the correct folder, we can initialize Git on that folder:

### Example
```bash
git init
```
**Output:**
```text
Initialized empty Git repository in /Users/user/myproject/.git/
```

You just created your first Git Repository!

### What is a Repository?
A Git repository is a folder that Git tracks for changes. The repository stores all your project's history and versions.

### What Happens When You Run `git init`?
Git creates a hidden folder called `.git` inside your project. This is where Git stores all the information it needs to track your files and history.

### Example: Show Hidden `.git` Folder (Linux/macOS)
```bash
ls -a
```
**Output:**
```text
.  ..  .git
```

On Windows, you may need to enable "Show hidden files" in File Explorer to see the `.git` folder.

## Troubleshooting

* **`git: command not found`**
  * **Solution:** Make sure Git is installed and added to your PATH. Restart your terminal if needed.
* **`Permission denied`**
  * **Solution:** Try running your terminal as administrator (Windows) or use `sudo` (macOS/Linux) if needed.

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `mkdir myproject` | Create a new directory named `myproject` |
| `cd myproject` | Change the working directory to `myproject` |
| `git init` | Initialize Git in the current folder, creating an empty Git repository |
| `ls -a` | Show all files in the current folder, including hidden files like `.git` |

---

# Git New Files

## What is a New File?

A new file is a file that you have created or copied into your project folder, but haven't told Git to watch.

Here are the key things to know:
* Create a new file (with a text editor)
* `ls` - List files in the folder
* `git status` - Check which files are tracked
* Understand untracked and tracked files

## Create a New File

Your new Git repository is empty.

Let's add a file using your favorite text editor, and save it in your project folder.

If you need help creating a file, see our HTML Editors page.

For this example, we'll use a simple HTML file:

### Example: Simple HTML File
```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
</head>
<body>

<h1>Hello world!</h1>
<p>This is the first file in my new Git Repo.</p>

</body>
</html>
```

Save this as `index.html` in your project folder.

## List Files in the Directory

To see which files are in your project folder, use the `ls` command:

### Example
```bash
ls
```
**Output:**
```text
index.html
```

`ls` lists all files in the current folder. You should see `index.html` in the output.

## Check File Status with `git status`

Now check if Git is tracking your new file:

### Example
```bash
git status
```
**Output:**
```text
On branch master

No commits yet

Untracked files:
  (use "git add ..." to include in what will be committed)
    index.html

nothing added to commit but untracked files present (use "git add" to track)
```

Git sees `index.html`, but it is untracked (not yet added to the repository).

### What is an Untracked File?
An untracked file is any file in your project folder that Git is not yet tracking. These are files you've created or copied into the folder, but haven't told Git to watch.

### What is a Tracked File?
A tracked file is a file that Git is watching for changes. To make a file tracked, you need to add it to the staging area (covered in the next chapter).

## Troubleshooting

* **File not showing up with `ls`:** Make sure you saved it in the correct folder. Use `pwd` to check your current directory.
* **File not listed in `git status`:** Make sure you are in the correct folder and that you saved the file.

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `ls` | Lists all files in the current directory |
| `git status` | Check the status of files in the repository (e.g., see untracked files) |
| `pwd` | Check your current working directory |

---

# Git Staging Environment

## What is the Staging Environment?

The staging environment (or staging area) is like a waiting room for your changes.

You use it to tell Git exactly which files you want to include in your next commit. This gives you control over what goes into your project history.

Here are some key commands for staging:
* `git add <file>` - Stage a file
* `git add --all` or `git add -A` - Stage all changes
* `git status` - See what is staged
* `git restore --staged <file>` - Unstage a file

## Stage a File with `git add`

To add a file to the staging area, use `git add <file>`:

### Example
```bash
git add index.html
```

Now `index.html` is staged. You can check what is staged with `git status`:

### Example
```bash
git status
```
**Output:**
```text
On branch master

No commits yet

Changes to be committed:
  (use "git restore --staged ..." to unstage)
    new file: index.html
```

## Stage Multiple Files (`git add --all`, `git add -A`)

You can stage all changes (new, modified, and deleted files) at once:

### Example
```bash
git add --all
```

> [!NOTE]
> **Note:** `git add -A` does the same thing as `git add --all`.

### Check Staged Files with `git status`
See which files are staged and ready to commit:

### Example
```bash
git status
```
**Output:**
```text
On branch master

No commits yet

Changes to be committed:
  (use "git restore --staged ..." to unstage)
        new file:   README.md
        new file:   bluestyle.css
        new file:   index.html
```

## How to Unstage a File

If you staged a file by mistake, you can remove it from the staging area (unstage it) with:

### Example
```bash
git restore --staged index.html
```

Now `index.html` is no longer staged. 

> [!NOTE]
> **Note:** You can also use `git reset HEAD index.html` for the same effect.

## Troubleshooting

* **Staged the wrong file?** Use `git restore --staged <file>` to unstage it.
* **Forgot to stage a file?** Just run `git add <file>` again before you commit.
* **Not sure what's staged?** Run `git status` to see what will be committed.

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `git add <file>` | Stage a specific file (e.g. `git add index.html`) |
| `git add --all` | Stage all changes (new, modified, and deleted files) at once |
| `git add -A` | Stage all changes (equivalent to `git add --all`) |
| `git status` | Check which files are staged, modified, or untracked |
| `git restore --staged <file>` | Unstage a file, removing it from the staging area (e.g. `git restore --staged index.html`) |
| `git reset HEAD <file>` | Unstage a file (alternative to `git restore --staged`, e.g. `git reset HEAD index.html`) |

---

# Git Commit

## What is a Commit?

A commit is like a save point in your project.

It records a snapshot of your files at a certain time, with a message describing what changed. You can always go back to a previous commit if you need to.

Here are some key commands for commits:
* `git commit -m "message"` - Commit staged changes with a message
* `git commit -a -m "message"` - Commit all tracked changes (skip staging)
* `git log` - See commit history

## How to Commit with a Message (`-m`)

To save your staged changes, use `git commit -m "your message"`:

### Example
```bash
git commit -m "First release of Hello World!"
```
**Output:**
```text
[master (root-commit) 221ec6e] First release of Hello World!
 3 files changed, 26 insertions(+)
 create mode 100644 README.md
 create mode 100644 bluestyle.css
 create mode 100644 index.html
```

Always write a clear message so you and others can understand what changed.

## Commit All Changes Without Staging (`-a`)

You can skip the staging step for already tracked files with `git commit -a -m "message"`. This commits all modified and deleted files, but not new/untracked files.

### Example
```bash
git commit -a -m "Quick update to README"
```
**Output:**
```text
[master 123abcd] Quick update to README
 1 file changed, 2 insertions(+)
```

> [!WARNING]
> **Warning:** Skipping the staging step can make you include unwanted changes. Use with care.

> [!NOTE]
> **Note:** `git commit -a` does not work for new/untracked files. You must use `git add <file>` first for new files.

### What happens if you try to commit a new file with `-a`?
```bash
git commit -a -m "Try to commit new file"
```
**Output:**
```text
On branch master

No commits yet

Untracked files:
  (use "git add ..." to include in what will be committed)
        index.html

nothing added to commit but untracked files present (use "git add" to track)
```

## Write Multi-line Commit Messages

If you just type `git commit` (no `-m`), your default editor will open so you can write a detailed, multi-line message:

### Example
```bash
git commit
```

Write a short summary on the first line, leave a blank line, then add more details below.

### Commit Message Best Practices:
* Keep the first line short (50 characters or less).
* Use the imperative mood (e.g., "Add feature" not "Added feature").
* Leave a blank line after the summary, then add more details if needed.
* Describe *why* the change was made, not just *what* changed.

## Other Useful Commit Options

* **Create an empty commit:**
  ```bash
  git commit --allow-empty -m "Start project"
  ```
* **Use previous commit message (no editor):**
  ```bash
  git commit --no-edit
  ```
* **Quickly add staged changes to last commit, keep message:**
  ```bash
  git commit --amend --no-edit
  ```

## Troubleshooting Common Commit Mistakes

* **Forgot to stage a file?**
  If you run `git commit -m "message"` but forgot to `git add` a file, just add it and commit again. Or use `git commit --amend` to add it to your last commit.
* **Typo in your commit message?**
  Use `git commit --amend -m "Corrected message"` to fix the last commit message.
* **Accidentally committed the wrong files?**
  You can use `git reset --soft HEAD~1` to undo the last commit and keep your changes staged.

## View Commit History (`git log`)

To view the history of commits for a repository, you can use the `git log` command:

### Example
```bash
git log
```
**Output:**
```text
commit 09f4acd3f8836b7f6fc44ad9e012f82faf861803 (HEAD -> master)
Author: w3schools-test 
Date:   Fri Mar 26 09:35:54 2021 +0100

    Updated index.html with a new line

commit 221ec6e10aeedbfd02b85264087cd9adc18e4b26
Author: w3schools-test 
Date:   Fri Mar 26 09:13:07 2021 +0100

    First release of Hello World!
```

For a shorter view, use `git log --oneline`:

### Example
```bash
git log --oneline
```
**Output:**
```text
09f4acd Updated index.html with a new line
221ec6e First release of Hello World!
```

To see which files changed in each commit, use `git log --stat`:

### Example
```bash
git log --stat
```

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `git commit -m "message"` | Commit staged changes with a specified message |
| `git commit -a -m "message"` | Commit all tracked changes, skipping the staging step |
| `git commit` | Open the default text editor to write a detailed, multi-line commit message |
| `git commit --allow-empty -m "message"` | Create an empty commit |
| `git commit --no-edit` | Complete a commit using the previous commit message without opening the editor |
| `git commit --amend --no-edit` | Add staged changes to the last commit without changing its message |
| `git commit --amend` | Amend the last commit (e.g. to add forgotten files) |
| `git commit --amend -m "message"` | Correct the message of the last commit |
| `git reset --soft HEAD~1` | Undo the last commit, keeping your changes in the staging area |
| `git log` | View the detailed history of commits for a repository |
| `git log --oneline` | View a brief, single-line summary of commits |
| `git log --stat` | View commit history showing files changed and insertion/deletion statistics |

---

# Git Tagging

## Key Commands for Tagging

* `git tag <tagname>` - Create a lightweight tag
* `git tag -a <tagname> -m "message"` - Create an annotated tag
* `git tag <tagname> <commit-hash>` - Tag a specific commit
* `git tag` - List tags
* `git show <tagname>` - Show tag details

## What is a Tag?

A tag in Git is like a label or bookmark for a specific commit.

Tags are most often used to mark important points in your project history, like releases (`v1.0` or `v2.0`). Tags are a simple and reliable way to keep track of versions and share them with your team or users.

Some common tag types include:
* **Releases**: Tags let you mark when your project is ready for release, so you (and others) can always find that exact version later.
* **Milestones**: Use tags to highlight major milestones, like when a big feature is finished or a bug is fixed.
* **Deployment**: Many deployment tools use tags to know which version of your code to deploy.
* **Hotfixes**: If you need to fix an old version, tags make it easy to check out and patch the right code.

## Create a Lightweight Tag

A lightweight tag is just a name for a commit. It's quick and simple, but does not store extra information.

### Annotated vs Lightweight Tags
* **Annotated Tag**: Stores author, date, and message. Recommended for releases and sharing with others.
* **Lightweight Tag**: Just a simple name for a commit (no extra info, like a bookmark).

### Example
```bash
git tag v1.0
```

## Create an Annotated Tag (`-a -m`)

An annotated tag stores your name, the date, and a message. This is recommended for most uses.

### Example
```bash
git tag -a v1.0 -m "Version 1.0 release"
```

## Tag a Specific Commit

You can tag an older commit by specifying its hash:

### Example
```bash
git tag v1.1 1a2b3c4d
```
Replace `1a2b3c4d` with the commit hash you want to tag.

## List Tags

See all tags in your repository:

### Example
```bash
git tag
```

## Show Tag Details (`git show`)

See details about a tag and the commit it points to:

### Example
```bash
git show v1.0
```

## Push Tags to Remote

By default, tags exist only on your local computer. If you want others to see your tags, you need to push them to your remote repository. If you don't push your tags, only you will see them, and only locally.

To push a single tag to your remote repository (for example, after creating a release tag):

### Example: Push a Single Tag
```bash
git push origin v1.0
```

> [!NOTE]
> **Did you know?** Pushing commits with `git push` does not push your tags! You must push tags explicitly as shown above.

To push all your local tags to the remote at once (useful if you've created several tags):

### Example: Push All Tags
```bash
git push --tags
```

## Delete Tags

Delete a tag locally:

### Example
```bash
git tag -d v1.0
```

Delete a tag from the remote repository:

### Example
```bash
git push origin --delete tag v1.0
```

## Update or Replace a Tag (Force Push)

If you need to move a tag to a different commit and update the remote, use `--force`:

### Example
```bash
git tag -f v1.0 <new-commit-hash>
git push --force origin v1.0
```

## Tagging Best Practices

* Use tags to mark releases, major milestones, or stable points in your project.
* Always use annotated tags (with `-a -m`) for anything public or shared.
* Create tags after passing all tests or before deploying/releasing code.

## Troubleshooting

* **Tag already exists?** Use `git tag -d <tagname>` to delete it, then re-create.
* **Pushed the wrong tag?** Delete it locally and remotely, then push the correct tag.
* **Tag not showing on remote?** Remember to push tags with `git push origin <tagname>` or `git push --tags`.
* **Need to overwrite a tag on the remote?** You can force-push a tag with `git push --force origin <tagname>`, but be careful! This will overwrite the tag for everyone using the remote.

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `git tag <tagname>` | Create a lightweight tag (e.g. `git tag v1.0`) |
| `git tag -a <tagname> -m "message"` | Create an annotated tag with author info, date, and a message |
| `git tag <tagname> <commit-hash>` | Create a tag pointing to a specific older commit hash |
| `git tag` | List all tags in the local repository |
| `git show <tagname>` | Show details of a tag and its corresponding commit |
| `git push origin <tagname>` | Push a specific tag to the remote repository (e.g. `git push origin v1.0`) |
| `git push --tags` | Push all local tags to the remote repository |
| `git tag -d <tagname>` | Delete a tag locally (e.g. `git tag -d v1.0`) |
| `git push origin --delete tag <tagname>` | Delete a tag from the remote repository (e.g. `git push origin --delete tag v1.0`) |
| `git tag -f <tagname> <new-commit-hash>` | Force recreate or update a tag to point to a new commit hash |
| `git push --force origin <tagname>` | Force push a tag update to the remote repository |

---

# Git Stash

## Key Commands for Stashing

* `git stash` - Stash your changes
* `git stash push -m "message"` - Stash with a message
* `git stash list` - List all stashes
* `git stash branch <branchname>` - Create a branch from a stash

## What is Git Stash? Why Use It?

Sometimes you need to quickly switch tasks or fix a bug, but you're not ready to commit your work.

`git stash` lets you save your uncommitted changes and return to a clean working directory. You can come back and restore your changes later.

Here are some common use cases:
* **Switch branches safely**: Save your work before changing branches.
* **Handle emergencies**: Stash your work to fix something urgent, then restore it.
* **Keep your work-in-progress safe**: Avoid messy commits or losing changes.

## Stash Your Changes (`git stash`)

Save your current changes (both staged and unstaged tracked files) with:

### What gets stashed?
* **Tracked files** (both staged and unstaged) are stashed by default.
* **Untracked files** (new files not yet added to Git) are not stashed by default. To stash untracked files too, use `git stash -u` (or `--include-untracked`).

### Example: Stash Your Work
```bash
git stash
```
**Output:**
```text
Saved working directory and index state WIP on main: 1234567 Add new feature
```
This command saves your changes and cleans your working directory so you can safely switch tasks or branches.

Your changes are now saved in a stack.

### What is a stash stack?
Each time you run `git stash`, your changes are saved on top of a "stack". The most recent stash is on top, and you can apply or drop stashes from the top down, or pick a specific one from the list.

Your working directory is clean, and you can switch branches or pull updates safely.

## Stash with a Message (`git stash push -m`)

Add a message to remember what you stashed:

### Example: Stash with a Message
```bash
git stash push -m "WIP: homepage redesign"
```
**Output:**
```text
Saved working directory and index state On main: WIP: homepage redesign
```
This command lets you add a descriptive message to your stash so you can remember what you were working on.

## List All Stashes (`git stash list`)

See all your saved stashes:

### Example: List Stashes
```bash
git stash list
```
**Output:**
```text
stash@{0}: On main: WIP: homepage redesign
stash@{1}: WIP on main: 1234567 Add new feature
```
This command shows all the stashes you have saved so far, with their names and messages.

## Show Stash Details (`git stash show`)

See what was changed in the latest stash:

### Example: Show Latest Stash
```bash
git stash show
```
**Output:**
```text
 src/index.html | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```
This command gives a summary of what files and changes are in your most recent stash.

To see a full diff:

### Example: Show Full Diff
```bash
git stash show -p
```
**Output:**
```diff
diff --git a/src/index.html b/src/index.html
index 1234567..89abcde 100644
--- a/src/index.html
+++ b/src/index.html
@@ ...
```
This command shows the exact lines that were changed in your most recent stash.

## Apply the Latest Stash (`git stash apply`)

Restore your most recent stashed changes (keeps the stash in the stack):

### Example: Apply Latest Stash
```bash
git stash apply
```
**Output:**
```text
On branch main
Changes not staged for commit:
  (use "git add ..." to update what will be committed)
  (use "git restore ..." to discard changes in working directory)
    modified:   src/index.html
```
This command restores your most recent stashed changes, but keeps the stash in the list so you can use it again if needed.

## Apply a Specific Stash (`git stash apply stash@{n}`)

Restore a specific stash from the list:

### Example: Apply a Specific Stash
```bash
git stash apply stash@{1}
```
**Output:**
```text
On branch main
Changes not staged for commit:
    modified:   src/index.html
```
This command lets you restore a specific stash from your list, not just the most recent one.

## Pop the Stash (`git stash pop`)

Apply the latest stash and remove it from the stack:

### Example: Pop the Stash
```bash
git stash pop
```
**Output:**
```text
On branch main
Changes not staged for commit:
    modified:   src/index.html
Dropped refs/stash@{0} (abc1234d5678)
```
This command restores your most recent stash and removes it from the list at the same time.

## Drop a Stash (`git stash drop`)

Delete a specific stash when you no longer need it:

### Example: Drop a Stash
```bash
git stash drop stash@{0}
```
**Output:**
```text
Dropped stash@{0} (abc1234d5678)
```
This command deletes a specific stash from your list when you no longer need it.

## Clear All Stashes (`git stash clear`)

Delete all your stashes at once:

### Example: Clear All Stashes
```bash
git stash clear
```
This command deletes all your stashes at once. Be careful! This cannot be undone!

## Branch from a Stash (`git stash branch`)

Create a new branch and apply a stash to it. Useful if your stashed work should become its own feature branch:

### Example: Branch from a Stash
```bash
git stash branch new-feature stash@{0}
```
**Output:**
```text
Switched to a new branch 'new-feature'
On branch new-feature
Changes not staged for commit:
    modified:   src/index.html
Dropped stash@{0} (abc1234d5678)
```
This command creates a new branch and applies your stashed changes to it. This is useful if you decide your work should become its own feature branch.

## Best Practices for Stashing

* Use clear messages when stashing: `git stash push -m "WIP: feature name"`
* Don't use stashes as long-term storage—commit your work when possible.
* Check your stash list regularly and clean up old stashes you no longer need.

## Troubleshooting

* **Did you lose your changes?** Try `git stash list` and `git stash apply` to recover stashed work.
* **Stash didn't apply cleanly?** You may need to resolve conflicts, just like a merge. Git will mark the conflicts in your files for you to resolve.
* **Untracked files missing?** By default, untracked files are not stashed. If you need to stash them, use `git stash -u` next time.
* **Accidentally cleared all stashes?** Unfortunately, `git stash clear` is permanent. Always double-check before running it!

> [!NOTE]
> **Note:** Stashes are useful for temporary work, but are not a replacement for commits!

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `git stash` | Stash staged and unstaged tracked changes, cleaning the working directory |
| `git stash -u` / `git stash --include-untracked` | Stash changes including untracked files |
| `git stash push -m "message"` | Stash changes with a descriptive message |
| `git stash list` | List all saved stashes |
| `git stash show` | Show a summary of file changes in the latest stash |
| `git stash show -p` | Show the full patch diff of changes in the latest stash |
| `git stash apply` | Restore the most recent stashed changes, keeping it in the stash list |
| `git stash apply stash@{n}` | Restore a specific stash (indexed by `n`) from the stash list |
| `git stash pop` | Restore the most recent stash and remove it from the stash list |
| `git stash drop stash@{n}` | Delete a specific stash from the stash list |
| `git stash clear` | Delete all saved stashes permanently |
| `git stash branch <branchname>` / `git stash branch new-feature stash@{0}` | Create a new branch and apply stashed changes to it |

---

# Git History

## What is Git History? Why Use It?

Git keeps a detailed record of every change made to your project.

You can use history commands to see what changed, when, and who made the change. This is useful for tracking progress, finding bugs, and understanding your project's evolution.

### Key Commands for Viewing History
* `git log` - Show full commit history
* `git log --oneline` - Show a summary of commits
* `git show <commit>` - Show details of a specific commit
* `git diff` - See unstaged changes
* `git diff --staged` - See staged changes

## Best Practices for Viewing History

* Make frequent, meaningful commits to keep your history clear.
* Write clear commit messages so you and your team can understand changes later.
* Use `git log --oneline` for a quick overview of your commit history.
* Use `git diff` before committing to review your work.

## See Commit History (`git log`)

Show a detailed list of all commits in your repository:

### Example: Full Commit History
```bash
git log
```
**Output:**
```text
commit 09f4acd3f8836b7f6fc44ad9e012f82faf861803 (HEAD -> master)
Author: w3schools-test 
Date:   Fri Mar 26 09:35:54 2021 +0100

    Updated index.html with a new line
```
This command shows all commits, including author, date, and message.

Use the arrow keys to scroll, and press `q` to quit.

> [!TIP]
> **Tip:** While viewing the log, you can search for a word by typing `/` followed by your search term (for example, `/fix`), then press `n` to jump to the next match. Press `q` at any time to quit.

## Show Commit Details (`git show <commit>`)

See all the details and changes for a specific commit:

### Example: Show Commit Details
```bash
git show 09f4acd
```
**Output:**
```diff
commit 09f4acd3f8836b7f6fc44ad9e012f82faf861803 (HEAD -> master)
Author: w3schools-test 
Date:   Fri Mar 26 09:35:54 2021 +0100

    Updated index.html with a new line

diff --git a/index.html b/index.html
index 1234567..89abcde 100644
--- a/index.html
+++ b/index.html
@@ ...
+New Title
```
This command shows everything about a commit: who made it, when, the message, and the exact changes.

## Compare Changes (`git diff`)

See what is different between your working directory and the last commit (unstaged changes):

### Example: See Unstaged Changes
```bash
git diff
```
**Output:**
```diff
diff --git a/index.html b/index.html
index 1234567..89abcde 100644
--- a/index.html
+++ b/index.html
@@ ...
-Old Title
+New Title
```
This command shows changes you have made but not yet staged for commit.

## Compare Staged Changes (`git diff --staged`)

See what is different between your staged files and the last commit:

### Example: See Staged Changes
```bash
git diff --staged
```
**Output:**
```diff
diff --git/index.html b/index.html
index 1234567..89abcde 100644
--- a/index.html
+++ b/index.html
@@ ...
-Old Title
+New Title
```
This command shows changes that are staged and ready to be committed.

## Compare Two Commits (`git diff <commit1> <commit2>`)

See what changed between any two commits:

### Example: Compare Two Commits
```bash
git diff 1234567 89abcde
```
**Output:**
```diff
diff --git/index.html b/index.html
index 1234567..89abcde 100644
--- a/index.html
+++ b/index.html
@@ ...
-Old Title
+New Title
```
This command shows the differences between two specific commits.

## Show a Summary of Commits (`git log --oneline`)

Show a short summary of each commit (great for a quick overview):

### Example: Oneline Log
```bash
git log --oneline
```
**Output:**
```text
09f4acd Updated index.html with a new line
8e7b2c1 Add about page
1a2b3c4 Initial commit
```
This command shows each commit on a single line for easy reading.

## Show Commits by Author (`git log --author="Alice"`)

See only the commits made by a specific author:

### Example: Commits by Author
```bash
git log --author="Alice"
```
**Output:**
```text
commit 1a2b3c4d5e6f7g8h9i0j
Author: Alice 
Date:   Mon Mar 22 10:12:34 2021 +0100

    Add about page
```
This command filters the log to show only commits by the author you specify.

## Show Recent Commits (`git log --since="2 weeks ago"`)

See only commits made in the last two weeks:

### Example: Recent Commits
```bash
git log --since="2 weeks ago"
```
**Output:**
```text
commit 09f4acd3f8836b7f6fc44ad9e012f82faf861803
Author: w3schools-test 
Date:   Fri Mar 26 09:35:54 2021 +0100

    Updated index.html with a new line
```
This command shows only the commits made in a recent time frame.

## Show Files Changed Per Commit (`git log --stat`)

See which files were changed in each commit and how many lines were added or removed:

### Example: Log with Stats
```bash
git log --stat
```
**Output:**
```text
commit 09f4acd3f8836b7f6fc44ad9e012f82faf861803
Author: w3schools-test 
Date:   Fri Mar 26 09:35:54 2021 +0100

    Updated index.html with a new line

index.html | 2 +-
1 file changed, 1 insertion(+), 1 deletion(-)
```
This command adds a summary of file changes to each commit in the log.

## Show a Branch Graph (`git log --graph`)

See a simple ASCII graph of your branch history (great for visualizing merges):

### Example: Log with Graph
```bash
git log --graph --oneline
```
**Output:**
```text
* 09f4acd Updated index.html with a new line
* 8e7b2c1 Add about page
|\
| * aabbccd Merge branch 'feature-x'
|/
```
This command shows a simple graph of your branch and merge history.

## Troubleshooting

* **Can't see your changes?** Make sure you have committed your work. Uncommitted changes won't appear in the history.
* **Log is too long?** Use `git log --oneline` or `git log --since` to make it easier to read.
* **How do I quit the log view?** Press `q` to exit the log or diff view.

> [!NOTE]
> **Note:** Exploring your history helps you understand what changed, when, and why.

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `git log` | Show the detailed commit history (author, date, message) |
| `git log --oneline` | Show a brief, single-line summary of commits |
| `git show <commit>` | Show details and diff of a specific commit (e.g. `git show 09f4acd`) |
| `git diff` | Show changes in the working directory compared to the last commit (unstaged changes) |
| `git diff --staged` | Show changes staged for the next commit compared to the last commit |
| `git diff <commit1> <commit2>` | Show changes between two specific commits (e.g. `git diff 1234567 89abcde`) |
| `git log --author="<author>"` | Filter commit history to show only commits by a specific author |
| `git log --since="<time-frame>"` | Filter commit history to show commits since a specific time frame (e.g. `2 weeks ago`) |
| `git log --stat` | Show commit history with file change and insertion/deletion statistics |
| `git log --graph` / `git log --graph --oneline` | Show commit history with an ASCII graph representing branch/merge structure |

---

# Git Help

## Why and When to Use Git Help?

Git has many commands and options.

If you forget how a command works or want to learn about its options, you can use Git's built-in help. This is the fastest way to get answers without leaving your terminal.

### Key Commands for Getting Help
* `git help <command>` - See the manual page for a command
* `git <command> --help` - See help for a command (same as above)
* `git <command> -h` - See a quick summary of options
* `git help --all` - List all possible Git commands
* `git help -g` - List guides and concepts

## See Help for a Specific Command (`git help <command>`)

Shows the full manual page for a specific command, including all options and examples:

### Example: See Help for Commit
```bash
git help commit
```
**Output:**
```text
GIT-COMMIT(1)
NAME
    git-commit - Record changes to the repository
SYNOPSIS
    git commit [options] [--] ...
DESCRIPTION
    Stores the current contents of the index in a new commit
    together with a log message from the user describing the changes.
...
```
This command opens the full documentation for `git commit` in your terminal.

> [!TIP]
> **Tip: While viewing help pages:**
> * Use the arrow keys or Space to scroll down, `b` to scroll up.
> * Type `/` followed by a word to search (e.g., `/option`), then `n` for the next match.
> * Press `q` at any time to quit the help view.

## See Help with `--help` (`git <command> --help`)

This does the same as `git help <command>`. Most users prefer this form:

### Example: See Help for Status
```bash
git status --help
```
**Output:**
```text
GIT-STATUS(1)
NAME
    git-status - Show the working tree status
SYNOPSIS
    git status [options] [--] [pathspec...]
DESCRIPTION
    Displays paths that have differences between the index file and the current HEAD commit.
...
```
This command opens the manual page for `git status`.

## See a Quick Summary with `-h` (`git <command> -h`)

Shows a short summary of the command's options, right in the terminal window (does not open the full manual):

### Example: Quick Help for Add
```bash
git add -h
```
**Output:**
```text
usage: git add [options] [--] ...
    -n, --dry-run         dry run
    -v, --verbose        be verbose
    -i, --interactive    interactive picking
    -p, --patch          select hunks interactively
    -e, --edit           edit current diff and apply
    -u, --update         update tracked files
    -A, --all            add changes from all tracked and untracked files
...
```
This command gives you a brief overview of available options for a command.

## List All Git Commands (`git help --all`)

Lists every Git command available on your system, grouped by category:

> [!WARNING]
> **Warning:** This will display a very long list of commands.

### Example
```bash
git help --all
```
**Output:**
```text
See 'git help ' to read about a specific subcommand

Main Porcelain Commands
   add                  Add file contents to the index
   am                   Apply a series of patches from a mailbox
   archive              Create an archive of files from a named tree
   bisect               Use binary search to find the commit that introduced a bug
   branch               List, create, or delete branches
   bundle               Move objects and refs by archive
   checkout             Switch branches or restore working tree files
   cherry-pick          Apply the changes introduced by some existing commits
   citool               Graphical alternative to git-commit
   clean                Remove untracked files from the working tree
   clone                Clone a repository into a new directory
   commit               Record changes to the repository
   describe             Give an object a human readable name based on an available ref
   diff                 Show changes between commits, commit and working tree, etc
   fetch                Download objects and refs from another repository
   format-patch         Prepare patches for e-mail submission
   gc                   Cleanup unnecessary files and optimize the local repository
   gitk                 The Git repository browser
   grep                 Print lines matching a pattern
   gui                  A portable graphical interface to Git
   init                 Create an empty Git repository or reinitialize an existing one
   log                  Show commit logs
   maintenance          Run tasks to optimize Git repository data
   merge                Join two or more development histories together
   mv                   Move or rename a file, a directory, or a symlink
   notes                Add or inspect object notes
   pull                 Fetch from and integrate with another repository or a local branch
   push                 Update remote refs along with associated objects
   range-diff           Compare two commit ranges (e.g. two versions of a branch)
   rebase               Reapply commits on top of another base tip
   reset                Reset current HEAD to the specified state
   restore              Restore working tree files
   revert               Revert some existing commits
   rm                   Remove files from the working tree and from the index
   shortlog             Summarize 'git log' output
   show                 Show various types of objects
   sparse-checkout      Initialize and modify the sparse-checkout
   stash                Stash the changes in a dirty working directory away
   status               Show the working tree status
   submodule            Initialize, update or inspect submodules
   switch               Switch branches
   tag                  Create, list, delete or verify a tag object signed with GPG
   worktree             Manage multiple working trees

Ancillary Commands / Manipulators
   config               Get and set repository or global options
   fast-export          Git data exporter
   fast-import          Backend for fast Git data importers
   filter-branch        Rewrite branches
   mergetool            Run merge conflict resolution tools to resolve merge conflicts
   pack-refs            Pack heads and tags for efficient repository access
   prune                Prune all unreachable objects from the object database
   reflog               Manage reflog information
   remote               Manage set of tracked repositories
   repack               Pack unpacked objects in a repository
   replace              Create, list, delete refs to replace objects

Ancillary Commands / Interrogators
   annotate             Annotate file lines with commit information
   blame                Show what revision and author last modified each line of a file
   bugreport            Collect information for user to file a bug report
   count-objects        Count unpacked number of objects and their disk consumption
   difftool             Show changes using common diff tools
   fsck                 Verifies the connectivity and validity of the objects in the database
   gitweb               Git web interface (web frontend to Git repositories)
   help                 Display help information about Git
   instaweb             Instantly browse your working repository in gitweb
   merge-tree           Show three-way merge without touching index
   rerere               Reuse recorded resolution of conflicted merges
   show-branch          Show branches and their commits
   verify-commit        Check the GPG signature of commits
   verify-tag           Check the GPG signature of tags
   whatchanged          Show logs with difference each commit introduces

Interacting with Others
   archimport           Import a GNU Arch repository into Git
   cvsexportcommit      Export a single commit to a CVS checkout
   cvsimport            Salvage your data out of another SCM people love to hate
   cvsserver            A CVS server emulator for Git
   imap-send            Send a collection of patches from stdin to an IMAP folder
   p4                   Import from and submit to Perforce repositories
   quiltimport          Applies a quilt patchset onto the current branch
   request-pull         Generates a summary of pending changes
   send-email           Send a collection of patches as emails
   svn                  Bidirectional operation between a Subversion repository and Git

Low-level Commands / Manipulators
   apply                Apply a patch to files and/or to the index
   checkout-index       Copy files from the index to the working tree
   commit-graph         Write and verify Git commit-graph files
   commit-tree          Create a new commit object
   hash-object          Compute object ID and optionally creates a blob from a file
   index-pack           Build pack index file for an existing packed archive
   merge-file           Run a three-way file merge
   merge-index          Run a merge for files needing merging
   mktag                Creates a tag object
   mktree               Build a tree-object from ls-tree formatted text
   multi-pack-index     Write and verify multi-pack-indexes
   pack-objects         Create a packed archive of objects
   prune-packed         Remove extra objects that are already in pack files
   read-tree            Reads tree information into the index
   symbolic-ref         Read, modify and delete symbolic refs
   unpack-objects       Unpack objects from a packed archive
   update-index         Register file contents in the working tree to the index
   update-ref           Update the object name stored in a ref safely
   write-tree           Create a tree object from the current index

Low-level Commands / Interrogators
   cat-file             Provide content or type and size information for repository objects
   cherry               Find commits yet to be applied to upstream
   diff-files           Compares files in the working tree and the index
   diff-index           Compare a tree to the working tree or index
   diff-tree            Compares the content and mode of blobs found via two tree objects
   for-each-ref         Output information on each ref
   for-each-repo        Run a Git command on a list of repositories
   get-tar-commit-id    Extract commit ID from an archive created using git-archive
   ls-files             Show information about files in the index and the working tree
   ls-remote            List references in a remote repository
   ls-tree              List the contents of a tree object
   merge-base           Find as good common ancestors as possible for a merge
   name-rev             Find symbolic names for given revs
   pack-redundant       Find redundant pack files
   rev-list             Lists commit objects in reverse chronological order
   rev-parse            Pick out and massage parameters
   show-index           Show packed archive index
   show-ref             List references in a local repository
   unpack-file          Creates a temporary file with a blob's contents
   var                  Show a Git logical variable
   verify-pack          Validate packed Git archive files

Low-level Commands / Syncing Repositories
   daemon               A really simple server for Git repositories
   fetch-pack           Receive missing objects from another repository
   http-backend         Server side implementation of Git over HTTP
   send-pack            Push objects over Git protocol to another repository
   update-server-info   Update auxiliary info file to help dumb servers

Low-level Commands / Internal Helpers
   check-attr           Display gitattributes information
   check-ignore         Debug gitignore / exclude files
   check-mailmap        Show canonical names and email addresses of contacts
   check-ref-format     Ensures that a reference name is well formed
   column               Display data in columns
   credential           Retrieve and store user credentials
   credential-cache     Helper to temporarily store passwords in memory
   credential-store     Helper to store credentials on disk
   fmt-merge-msg        Produce a merge commit message
   interpret-trailers   Add or parse structured information in commit messages
   mailinfo             Extracts patch and authorship from a single e-mail message
   mailsplit            Simple UNIX mbox splitter program
   merge-one-file       The standard helper program to use with git-merge-index
   patch-id             Compute unique ID for a patch
   sh-i18n              Git's i18n setup code for shell scripts
   sh-setup             Common Git shell script setup code
   stripspace           Remove unnecessary whitespace

External commands
   askyesno
   credential-helper-selector
   flow
   lfs
```

> [!NOTE]
> **Note:** If you find yourself stuck in the list view, press `SHIFT + G` to jump to the end of the list, then `q` to exit the view.

## List Guides and Concepts (`git help -g`)

Shows a list of guides and concept topics for deeper learning:

### Example: List Guides and Concepts
```bash
git help -g
```
**Output:**
```text
The common Git guides are:
   attributes   Defining attributes per path
   everyday     Everyday Git With 20 Commands Or So
   glossary     A Git glossary of terms
   revisions    Specifying revisions and ranges for Git
...
```
This command is great for learning about Git's advanced concepts and best practices.

## Troubleshooting

* **How do I quit the help viewer?** Press `q` to exit the help page.
* **Help page won't open?** Try `git <command> -h` for a quick summary instead.
* **How do I search for a word?** In the help viewer, press `/` then type your search term and press Enter.

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `git help <command>` | See the full manual page for a specific command (e.g. `git help commit`) |
| `git <command> --help` | See the full manual page for a command (equivalent to `git help <command>`, e.g. `git status --help`) |
| `git <command> -h` | See a quick summary of command options right in the terminal window (e.g. `git add -h`) |
| `git help --all` | List all possible Git commands available on your system |
| `git help -g` | List guides and concepts (e.g. glossary, revisions) for deeper learning |

---

# Git Branch

## What is a Git Branch?

In Git, a branch is like a separate workspace where you can make changes and try new ideas without affecting the main project. Think of it as a "parallel universe" for your code.

### Why Use Branches?
Branches let you work on different parts of a project, like new features or bug fixes, without interfering with the main branch.

### Common Reasons to Create a Branch
* Developing a new feature
* Fixing a bug
* Experimenting with ideas

### Example: With and Without Git
Let's say you have a large project, and you need to update the design on it. How would that work without and with Git:

#### Without Git
1. Make copies of all the relevant files to avoid impacting the live version.
2. Start working with the design and find that code depends on code in other files, that also need to be changed!
3. Make copies of the dependent files as well, making sure that every file dependency references the correct file name.
4. **EMERGENCY!** There is an unrelated error somewhere else in the project that needs to be fixed ASAP!
5. Save all your files, making a note of the names of the copies you were working on.
6. Work on the unrelated error and update the code to fix it.
7. Go back to the design, and finish the work there.
8. Copy the code or rename the files, so the updated design is on the live version.
9. (2 weeks later, you realize that the unrelated error was not fixed in the new design version because you copied the files before the fix).

#### With Git
1. With a new branch called `new-design`, edit the code directly without impacting the main branch.
2. **EMERGENCY!** There is an unrelated error somewhere else in the project that needs to be fixed ASAP!
3. Create a new branch from the main project called `small-error-fix`.
4. Fix the unrelated error and merge the `small-error-fix` branch with the main branch.
5. Go back to the `new-design` branch, and finish the work there.
6. Merge the `new-design` branch with main (getting alerted to the small error fix that you were missing).

* Branches allow you to work on different parts of a project without impacting the main branch.
* When the work is complete, a branch can be merged with the main project.
* You can even switch between branches and work on different projects without them interfering with each other.
* Branching in Git is very lightweight and fast!

## Creating a New Branch

Let's say you want to add a new feature. You can create a new branch for it.

Let's add some new features to our `index.html` page. We are working in our local repository, and we do not want to disturb or possibly wreck the main project. So we create a new branch:

### Example
```bash
git branch hello-world-images
```
Now we created a new branch called "hello-world-images".

## Listing All Branches

Let's confirm that we have created a new branch. To see all branches in your repository, use:

### Example
```bash
git branch
```
**Output:**
```text
  hello-world-images
* master
```
We can see the new branch with the name `hello-world-images`, but the `*` beside `master` specifies that we are currently on that branch.

## Switching Between Branches

`checkout` is the command used to check out a branch, moving us from the current branch to the one specified at the end of the command:

### Example
```bash
git checkout hello-world-images
```
**Output:**
```text
Switched to branch 'hello-world-images'
```
Now you can work in your new branch without affecting the main branch.

## Working in a Branch

Now we have moved our current workspace from the `master` branch to the new branch.

Open your favorite editor and make some changes. For this example, we added an image (`img_hello_world.jpg`) to the working folder and a line of code in the `index.html` file:

### Example
```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
<link rel="stylesheet" href="bluestyle.css">
</head>
<body>

<h1>Hello world!</h1>
<div><img src="img_hello_world.jpg" alt="Hello World from Space" style="width:100%;max-width:960px"></div>
<p>This is the first file in my new Git Repo.</p>
<p>A new line in our file!</p>

</body>
</html>
```

We have made changes to a file and added a new file in the working directory (same directory as the main branch).

Now check the status of the current branch:

### Example
```bash
git status
```
**Output:**
```text
On branch hello-world-images
Changes not staged for commit:
  (use "git add ..." to update what will be committed)
  (use "git restore ..." to discard changes in working directory)
        modified:   index.html

Untracked files:
  (use "git add ..." to include in what will be committed)
        img_hello_world.jpg

no changes added to commit (use "git add" and/or "git commit -a")
```

So let's go through what happens here:
1. There are changes to our `index.html`, but the file is not staged for commit.
2. `img_hello_world.jpg` is not tracked.

So we need to add both files to the Staging Environment for this branch:

### Example
```bash
git add --all
```
Using `--all` instead of individual filenames will Stage all changed (new, modified, and deleted) files.

Check the status of the branch:

### Example
```bash
git status
```
**Output:**
```text
On branch hello-world-images
Changes to be committed:
  (use "git restore --staged ..." to unstage)
    new file: img_hello_world.jpg
    modified: index.html
```

We are happy with our changes. So we will commit them to the branch:

### Example
```bash
git commit -m "Added image to Hello World"
```
**Output:**
```text
[hello-world-images 0312c55] Added image to Hello World
2 files changed, 1 insertion(+)
create mode 100644 img_hello_world.jpg
```
Now we have a new branch that is different from the `master` branch.

> [!NOTE]
> **Note:** Using the `-b` option on `checkout` will create a new branch, and move to it, if it does not exist.

## Switching Between Branches

Now let's see just how quick and easy it is to work with different branches, and how well it works.

We are currently on the branch `hello-world-images`. We added an image to this branch, so let's list the files in the current directory:

### Example
```bash
ls
```
**Output:**
```text
README.md  bluestyle.css  img_hello_world.jpg  index.html
```
We can see the new file `img_hello_world.jpg`, and if we open the html file, we can see the code has been altered. All is as it should be.

Now, let's see what happens when we change branch to `master`:

### Example
```bash
git checkout master
```
**Output:**
```text
Switched to branch 'master'
```

The new image is not a part of this branch. List the files in the current directory again:

### Example
```bash
ls
```
**Output:**
```text
README.md  bluestyle.css  index.html
```
`img_hello_world.jpg` is no longer there! And if we open the html file, we can see the code reverted to what it was before the alteration.

See how easy it is to work with branches? And how this allows you to work on different things?

## Emergency Branch

Now imagine that we are not yet done with `hello-world-images`, but we need to fix an error on `master`.

I don't want to mess with `master` directly, and I do not want to mess with `hello-world-images`, since it is not done yet.

So we create a new branch to deal with the emergency:

### Example
```bash
git checkout -b emergency-fix
```
**Output:**
```text
Switched to a new branch 'emergency-fix'
```
Now we have created a new branch from `master`, and changed to it. We can safely fix the error without disturbing the other branches.

Let's fix our imaginary error:

### Example
```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
<link rel="stylesheet" href="bluestyle.css">
</head>
<body>

<h1>Hello world!</h1>
<p>This is the first file in my new Git Repo.</p>
<p>This line is here to show how merging works.</p>

</body>
</html>
```

We have made changes in this file, and we need to get those changes to the `master` branch.

Check the status:

### Example
```bash
git status
```
**Output:**
```text
On branch emergency-fix
Changes not staged for commit:
  (use "git add ..." to update what will be committed)
  (use "git restore ..." to discard changes in working directory)
        modified:   index.html

no changes added to commit (use "git add" and/or "git commit -a")
```

Stage the file, and commit:

### Example
```bash
git add index.html
git commit -m "updated index.html with emergency fix"
```
**Output:**
```text
[emergency-fix dfa79db] updated index.html with emergency fix
 1 file changed, 1 insertion(+), 1 deletion(-)
```
Now we have a fix ready for `master`, and we need to merge the two branches.

## Deleting a Branch

When you're done with a branch, you can delete it:

### Example
```bash
git branch -d hello-world-images
```
This deletes the branch named `hello-world-images` (if it's already merged).

## Best Practices for Working with Branches

* Use clear, descriptive branch names (like `feature/login-page` or `bugfix/header-crash`).
* Keep each branch focused on a single purpose or feature.
* Regularly merge changes from the main branch to keep your branch up-to-date.
* Delete branches that are no longer needed to keep your repository clean.

## Practical Examples

* **Rename a branch**: `git branch -m old-name new-name`
* **List all branches**: `git branch`
* **Switch branches**: `git checkout branch-name` or `git switch branch-name`
* **Delete a branch (not merged)**: `git branch -D branch-name`
* **See which branch you're on**: `git status`

## Troubleshooting

* If you don't see your changes on the main branch, remember: changes in one branch stay there until you merge them.
* When deleting a branch, make sure it's merged first. If you try to delete an unmerged branch, Git will prevent you from doing so.
* To force delete an unmerged branch, use `git branch -D branch-name`.

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `git branch <branchname>` | Create a new branch named `<branchname>` |
| `git branch` | List all local branches in the repository |
| `git checkout <branchname>` | Switch from the current branch to `<branchname>` |
| `git checkout -b <branchname>` | Create a new branch named `<branchname>` and switch to it immediately |
| `git add --all` | Stage all changes (new, modified, and deleted files) in the current branch workspace |
| `git branch -d <branchname>` | Delete a merged branch named `<branchname>` |
| `git branch -D <branchname>` | Force delete an unmerged branch named `<branchname>` |
| `git branch -m <oldname> <newname>` | Rename a branch from `<oldname>` to `<newname>` |
| `git switch <branchname>` | Switch to branch `<branchname>` (alternative to checkout) |
| `ls` | List files in the current working directory |
| `git status` | Check status of the current branch (e.g. see current branch name, staged/unstaged changes) |

---

# Git Branch Merge

## What is Merging in Git?

Merging in Git means combining the changes from one branch into another. This is how you bring your work together after working separately on different features or bug fixes.

### Common `git merge` Options
* `git merge` - Merge a branch into your current branch
* `git merge --no-ff` - Always create a merge commit
* `git merge --squash` - Combine changes into a single commit
* `git merge --abort` - Abort a merge in progress

## Merging Branches (`git merge`)

To combine the changes from one branch into another, use `git merge`. Usually, you first switch to the branch you want to merge into (often `main` or `master`), then run the merge command with the branch name you want to combine in.

First, we need to change to the `master` branch:

### Example
```bash
git checkout master
```
**Output:**
```text
Switched to branch 'master'
```

Now we merge the current branch (`master`) with `emergency-fix`:

### Example
```bash
git merge emergency-fix
```
**Output:**
```text
Updating 09f4acd..dfa79db
Fast-forward
 index.html | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```
Since the `emergency-fix` branch came directly from `master`, and no other changes had been made to `master` while we were working, Git sees this as a continuation of `master`. So it can "Fast-forward", just pointing both `master` and `emergency-fix` to the same commit.

As `master` and `emergency-fix` are essentially the same now, we can delete `emergency-fix`, as it is no longer needed:

### Example
```bash
git branch -d emergency-fix
```
**Output:**
```text
Deleted branch emergency-fix (was dfa79db).
```

## Non-Fast-Forward Merge (`git merge --no-ff`)

By default, if your branch can be merged with a fast-forward (no new commits on the base), Git just moves the branch pointer forward. If you want to always create a merge commit (to keep history clearer), use `git merge --no-ff branchname`.

### Example
```bash
git merge --no-ff feature-branch
```
**Output:**
```text
Merge made by the 'recursive' strategy.
 index.html | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```

## Squash Merge (`git merge --squash`)

If you want to combine all the changes from a branch into a single commit (instead of keeping every commit), use `git merge --squash branchname`. This is useful for cleaning up commit history before merging.

### Example
```bash
git merge --squash feature-branch
```
**Output:**
```text
Squash commit -- not updating HEAD
Automatic merge went well; stopped before committing as requested
```

## Aborting a Merge (`git merge --abort`)

If you run into trouble during a merge (like a conflict you don't want to resolve), you can cancel the merge and go back to how things were before with `git merge --abort`.

### Example
```bash
git merge --abort
```

## What is a Merge Conflict?

A merge conflict happens when changes in two branches touch the same part of a file and Git doesn't know which version to keep. Think of it like two people editing the same sentence in a document in different ways—Git needs your help to decide which version to use.

### How to Resolve a Merge Conflict
1. Git will mark the conflict in your file.
2. You need to open the file, look for lines like `<<<<<<< HEAD` and `=======`, and decide what the final version should be.
3. Then, stage and commit your changes.

## Merge Conflict Example

Now we can move over to `hello-world-images` from the last chapter, and keep working. Add another image file (`img_hello_git.jpg`) and change `index.html` so it shows it:

### Example
```bash
git checkout hello-world-images
```
**Output:**
```text
Switched to branch 'hello-world-images'
```

### Example: Modify `index.html`
```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
<link rel="stylesheet" href="bluestyle.css">
</head>
<body>

<h1>Hello world!</h1>
<div><img src="img_hello_world.jpg" alt="Hello World from Space" style="width:100%;max-width:960px"></div>
<p>This is the first file in my new Git Repo.</p>
<p>A new line in our file!</p>
<div><img src="img_hello_git.jpg" alt="Hello Git" style="width:100%;max-width:640px"></div>

</body>
</html>
```

Now, we are done with our work here and can stage and commit for this branch:

### Example
```bash
git add --all
git commit -m "added new image"
```
**Output:**
```text
[hello-world-images 1f1584e] added new image
 2 files changed, 1 insertion(+)
 create mode 100644 img_hello_git.jpg
```
We see that `index.html` has been changed in both branches. Now we are ready to merge `hello-world-images` into `master`. But what will happen to the changes we recently made in `master`?

### Example
```bash
git checkout master
git merge hello-world-images
```
**Output:**
```text
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```
The merge failed, as there is conflict between the versions for `index.html`. Let us check the status:

### Example
```bash
git status
```
**Output:**
```text
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:
        new file:   img_hello_git.jpg
        new file:   img_hello_world.jpg

Unmerged paths:
  (use "git add ..." to mark resolution)
        both modified:   index.html
```
This confirms there is a conflict in `index.html`, but the image files are ready and staged to be committed. So we need to fix that conflict. Open the file in our editor:

### Example: Conflicted `index.html`
```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
<link rel="stylesheet" href="bluestyle.css">
</head>
<body>

<h1>Hello world!</h1>
<div><img src="img_hello_world.jpg" alt="Hello World from Space" style="width:100%;max-width:960px"></div>
<p>This is the first file in my new Git Repo.</p>
<<<<<<< HEAD
<p>This line is here to show how merging works.</p>
=======
<p>A new line in our file!</p>
<div><img src="img_hello_git.jpg" alt="Hello Git" style="width:100%;max-width:640px"></div>
>>>>>>> hello-world-images

</body>
</html>
```

We can see the differences between the versions and edit it like we want:

### Example: Resolved `index.html`
```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
<link rel="stylesheet" href="bluestyle.css">
</head>
<body>

<h1>Hello world!</h1>
<div><img src="img_hello_world.jpg" alt="Hello World from Space" style="width:100%;max-width:960px"></div>
<p>This is the first file in my new Git Repo.</p>
<p>This line is here to show how merging works.</p>
<div><img src="img_hello_git.jpg" alt="Hello Git" style="width:100%;max-width:640px"></div>

</body>
</html>
```

Now we can stage `index.html` and check the status:

### Example
```bash
git add index.html
git status
```
**Output:**
```text
On branch master
All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:
        new file:   img_hello_git.jpg
        new file:   img_hello_world.jpg
        modified:   index.html
```
The conflict has been fixed, and we can use commit to conclude the merge:

### Example
```bash
git commit -m "merged with hello-world-images after fixing conflicts"
```
**Output:**
```text
[master e0b6038] merged with hello-world-images after fixing conflicts
```

And delete the `hello-world-images` branch:

### Example
```bash
git branch -d hello-world-images
```
**Output:**
```text
Deleted branch hello-world-images (was 1f1584e).
```

Now you have a better understanding of how branches and merging works. Time to start working with a remote repository!

## Best Practices for Merging Branches

* Always commit or stash your changes before starting a merge.
* Regularly merge from the main branch into your feature branch to minimize conflicts.
* Read and resolve conflicts carefully—don't just accept all changes blindly.
* Write clear and descriptive merge commit messages.

## Practical Examples

* **Abort a merge**: `git merge --abort`
* **Check status during a merge**: `git status`
* **Resolve a conflict and complete the merge**: Edit the conflicted file(s), then `git add <file>` and `git commit`
* **Fast-forward merge**: Happens when no new commits diverged—Git just moves the branch pointer forward.
* **No-fast-forward merge**: Use `git merge --no-ff <branch>` to always create a merge commit, preserving branch history.

## Troubleshooting & Tips

* If you want to cancel a merge, use `git merge --abort`.
* Always commit or stash your changes before starting a merge.
* Read the conflict markers carefully and remove them after you've resolved the issue.
* Use `git status` to see what files need your attention.
* If you're unsure, ask a teammate or look up the error message.

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `git merge <branchname>` | Merge changes from `<branchname>` into the current branch |
| `git merge --no-ff <branchname>` | Merge `<branchname>` into the current branch and always create a merge commit |
| `git merge --squash <branchname>` | Combine all changes from `<branchname>` into a single commit to merge |
| `git merge --abort` | Cancel the merge in progress and revert to the pre-merge state |
| `git checkout <branchname>` | Switch to branch `<branchname>` (e.g. `git checkout master`) |
| `git branch -d <branchname>` | Delete a merged branch (e.g. `git branch -d emergency-fix`) |
| `git status` | Check current staging status and identify merge conflict locations |
| `git add <file>` | Stage a resolved file to mark the conflict as resolved (e.g. `git add index.html`) |
| `git commit` | Conclude the merge and save changes with a merge commit |

---

# Git Workflow

## Git Workflow Commands Overview

* **Working Directory**: Where you make changes
* `git add` - Stage changes
* `git commit` - Save changes to your repository
* `git push` - Share changes with others
* `git status` - Check what's going on
* **Undo/Amend** - Fix mistakes (`git restore`, `git reset`, `git commit --amend`)

> [!NOTE]
> **See Also:** GitHub Flow is a popular collaborative workflow for teams using GitHub. If you work with GitLab or Bitbucket, those platforms have their own workflows too.

## Understanding the Git Workflow

Git uses a distributed workflow that allows you to work on your code, stage changes, and commit them to your local repository before sharing with others. Understanding this workflow is essential for effective version control.

### The Three Areas of Git
* **Working Directory**: Where you make changes to your files.
* **Staging Area (Index)**: Where you prepare changes before committing.
* **Repository**: Where your committed history is stored.

### Workflow Diagram
```text
[Working Directory] --git add--> [Staging Area] --git commit--> [Repository]
```

## Working Directory

This is where you make changes to your files. Think of it as your workspace or desk. Files here can be new, modified, or deleted, but Git won't save these changes until you stage and commit them.

## Staging Changes (`git add`)

When you are happy with your changes, you "stage" them with `git add`. This puts your changes in the Staging Area, like putting your finished letter in an envelope.

### Example
```bash
git add index.html
```

To stage all changes (new, modified, and deleted files):
```bash
git add .
```

## Committing Changes (`git commit`)

Committing saves your staged changes to your local repository. It's like mailing your letter—you can't change it after it's sent!

### Example
```bash
git commit -m "Describe your changes"
```
You can also use `git commit -a -m "message"` to stage and commit all modified and deleted files in one step (but not new files).

## Pushing Changes (`git push`)

After you commit, your changes are only in your local repository. Use `git push` to send your commits to a remote repository (like GitHub or Bitbucket) so others can see them.

### Example
```bash
git push
```

## Checking Status (`git status`)

Use `git status` to see which files are staged, unstaged, or untracked. This helps you keep track of what you still need to add or commit.

### Example
```bash
git status
```

## Undoing and Amending Changes

Made a mistake? Git lets you fix things before you push!
* `git restore <file>` - Undo changes in your working directory (before staging).
* `git restore --staged <file>` - Unstage a file (move it out of the Staging Area).
* `git reset HEAD~` - Undo your last commit (keeps changes in your working directory).
* `git commit --amend` - Change the last commit message or add files to your last commit.

### Example: Unstage a file
```bash
git restore --staged index.html
```

## Best Practices for Git Workflow

* Commit frequently with clear, meaningful messages.
* Check your status often with `git status` to avoid surprises.
* Stage only what you intend to commit. Use `git add <file>` for precision.
* Push regularly to back up your work and share with others.
* Review your changes with `git diff` before committing.

## Tips & Troubleshooting

* Use `git status` often to see what's going on.
* If you commit the wrong thing, use `git reset` or `git commit --amend` before pushing.
* Stage only what you want to commit—use `git add <filename>` for specific files.
* Don't forget to push after committing, or your changes won't show up for others.
* If you're not sure, ask for help or look up the error message—everyone makes mistakes!

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `git add <file>` | Stage a specific file for the next commit (e.g. `git add index.html`) |
| `git add .` | Stage all changes (new, modified, and deleted files) in the current directory |
| `git commit -m "message"` | Save staged changes to the repository with a descriptive message |
| `git commit -a -m "message"` | Stage and commit all modified and deleted files in one step |
| `git push` | Send commits from the local repository to a remote repository |
| `git status` | Show the status of files in the working directory and staging area |
| `git restore <file>` | Undo changes in the working directory (discard local modifications before staging) |
| `git restore --staged <file>` | Remove a file from the staging area (unstage it) |
| `git reset HEAD~` | Undo the last local commit, keeping the changes in the working directory |
| `git commit --amend` | Change the last commit message or add new staged changes to it |

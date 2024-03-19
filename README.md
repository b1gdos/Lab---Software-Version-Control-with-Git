# Lab - Software Version Control with Git

## Objectives

- Part 1: Launch the DEVASC VM
- Part 2: Initializing Git
- Part 3: Staging and Committing a File in the Git Repository
- Part 4: Managing the File and Tracking Changes
- Part 5: Branches and Merging
- Part 6: Handling Merge Conflicts
- Part 7: Integrating Git with GitHub

## Background / Scenario

In this lab, you will explore the fundamentals of the distributed version control system Git, including most of the features you need to know in order to collaborate on a software project. You will also integrate your local Git repository with the cloud-based GitHub repository.

## Required Resources

- 1 PC with operating system of your choice
- Virtual Box or VMWare
- DEVASC Virtual Machine

## Instructions

### Part 1: Launch the DEVASC VM

If you have not already completed the Lab - Install the Virtual Machine Lab Environment, do so now. If you have already completed that lab, launch the DEVASC VM now.

### Part 2: Initializing Git

1. Open a terminal in the DEVASC-LABVM.
   - Double-click the Terminal Emulator icon on the desktop.

2. Initialize a Git Repository.
   - Use the `ls` command to display a listing of the current directory.
   - Configure user information:
     ```bash
     devasc@labvm:~$ git config --global user.name "SampleUser"
     devasc@labvm:~$ git config --global user.email sample@example.com
     ```
   - Review configuration with `git config --list`.
   - Navigate to the devnet-src folder:
     ```bash
     devasc@labvm:~$ cd labs/devnet-src/
     ```
   - Create and enter the `git-intro` directory:
     ```bash
     devasc@labvm:~/labs/devnet-src$ mkdir git-intro
     devasc@labvm:~/labs/devnet-src$ cd git-intro
     ```
   - Initialize the current directory as a Git repository:
     ```bash
     devasc@labvm:~/labs/devnet-src/git-intro$ git init
     ```

### Part 3: Staging and Committing a File in the Repository

1. Create a file.
   - Create the file `DEVASC.txt`:
     ```bash
     devasc@labvm:~/labs/devnet-src/git-intro$ echo "I am on my way to passing the Cisco DEVASC exam" > DEVASC.txt
     ```

2. Examine the Repository Status.
   - Check repository status with `git status`.

3. Staging the File.
   - Use `git add` to stage the `DEVASC.txt` file.
   - Check status again with `git status`.

4. Committing Changes and Viewing History

Now that you've made changes to your file and staged them, it's time to commit those changes and view the commit history.

## Step 4: Committing a File

After staging your changes, commit them to let Git know you want to start tracking those changes. Use the `git commit` command with the `-m` message switch to add a message explaining the changes you've made. Note the commit ID generated for your commit.

```bash
devasc@labvm:~/labs/devnet-src/git-intro$ git commit -m "Committing DEVASC.txt to begin tracking changes"
[master (root-commit) b510f8e] Committing DEVASC.txt to begin tracking changes
1 file changed, 1 insertion(+)
create mode 100644 DEVASC.txt
devasc@labvm:~/labs/devnet-src/git-intro$
```

## Step 5: Viewing the Commit History

Use the `git log` command to show all commits in the current branch's history. By default, all commits are made to the master branch. Each commit entry includes the commit hash, author information, date/time of the commit, and the commit message.

```bash
devasc@labvm:~/labs/devnet-src/git-intro$ git log
commit b510f8e5f9f63c97432d108a0413567552c07356 (HEAD -> master)
Author: Sample User <sample@example.com>
Date: Sat Apr 18 18:03:28 2020 +0000
 Committing DEVASC.txt to begin tracking changes
devasc@labvm:~/labs/devnet-src/git-intro$
```

Continue with the next steps as outlined in the lab instructions.
```
```markdown
# Branching, Merging, and Handling Merge Conflicts

This section guides you through creating branches, merging changes, and handling merge conflicts in Git.

## Step 1: Create a New Branch

Create a new branch called "feature" using the `git branch <branch-name>` command.

```bash
devasc@labvm:~/labs/devnet-src/git-intro$ git branch feature
```

## Step 2: Verify Current Branch

Verify the current branch and all branches available in the repository using the `git branch` command. The current branch is indicated by a "*".

```bash
devasc@labvm:~/labs/devnet-src/git-intro$ git branch
 feature
* master
```

## Step 3: Checkout the New Branch

Switch to the newly created "feature" branch using the `git checkout <branch-name>` command.

```bash
devasc@labvm:~/labs/devnet-src/git-intro$ git checkout feature
```

## Step 4: Verify Current Branch and Make Changes

Verify that you're now on the "feature" branch and make necessary changes to the file.

```bash
devasc@labvm:~/labs/devnet-src/git-intro$ git branch
* feature
 master
devasc@labvm:~/labs/devnet-src/git-intro$ echo "This text was added originally while in the feature branch" >> DEVASC.txt
```

## Step 5: Stage and Commit Changes in the Feature Branch

Stage and commit the changes made in the "feature" branch.

```bash
devasc@labvm:~/labs/devnet-src/git-intro$ git add DEVASC.txt
devasc@labvm:~/labs/devnet-src/git-intro$ git commit -m "Added a third line in feature branch"
```

## Step 6: Merge Feature Branch into Master

Merge the changes from the "feature" branch into the "master" branch.

```bash
devasc@labvm:~/labs/devnet-src/git-intro$ git checkout master
devasc@labvm:~/labs/devnet-src/git-intro$ git merge feature
```

## Step 7: Delete the Feature Branch

Once the changes are merged, delete the "feature" branch.

```bash
devasc@labvm:~/labs/devnet-src/git-intro$ git branch -d feature
```

## Handling Merge Conflicts

In case of merge conflicts, follow these steps to resolve them:

1. Attempt to merge branches.
2. Identify the conflicts using `git status`.
3. Manually edit the conflicted file to resolve conflicts.
4. Stage and commit the resolved file.

Continue with the steps outlined in the lab instructions for handling merge conflicts.
```

This markdown provides a clear guide for branching, merging, and handling merge conflicts in a GitHub README.md file. You can copy and paste it accordingly.

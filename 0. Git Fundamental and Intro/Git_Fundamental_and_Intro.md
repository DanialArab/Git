# Git Fundamental and Intro

## What is Git and why is it so popular?

Git is the most popular version control system in the world. A version control system records the changes to our code over time in a **special database called repository**. We can look at our project history and see who has made what changes, when, and why. And in case required we can easily revert our project back to an earlier stage. 
In a nutshell through using a version control system we can:

o	Track history and

o	Work together

Version control systems fall into two broad categories:

-	**Centralized**, the problem with this architecture is **single point of failure** meaning if the server goes offline we cannot collaborate or save snapshots of our project and so we have to wait until the server comes back online 
-	**Distributed**, in this system we don’t have the problem mentioned above with Centralized system, every team member has a copy of the project locally on their machine and if the central server goes offline we can synchronize our work directly with others. **Git and Mercurial** are examples of distributed version control systems.

Git is the most popular version control system in the world, it is almost everywhere: more than %90 of the software projects in the world use Git and so that is why in almost every software engineering job posting you see Git as a skill required, because Git is:

-	Free
-	Open source
-	Super fast
-	Scalable
-	Cheap branching/merging 

## How to use Git

- Command line (the fastest and easiest way to get the job done) 
- Code editors and IDEs
- Graphical User Interfaces built specifically for using Git, GitKraken Git GUI is Mosh’s favorite GUI for Git it is free for open source projects but for the commercial projects we have to pay annual fee

In this course we mostly use command line because:
- GUI tools have limitations, so you NEED to roll up your sleeves and use command line sometimes
- GUI tools are **not always available BUT command line is always available**. You may connect to a server remotely and you may not have permission to install a GUI tool and in these situations if you don’t know how to use command line you are in trouble 

The best practice is know how to use Git using command line and use both approaches: using command line and GUI tool. There are times which makes sense using a GUI tool and not a command line but other times using a command line is faster and easier. In summary we should use the right tool for the job. So we use mostly command line except some times when using a GUI tool makes a better sense. 

## Git configuration

The first time we need to set up some settings like:
- Name
- Email
- Default editor
- Line ending, very important one 

We can specify these settings at three different levels:

- System, at the top level the settings we apply here apply to all users of the current computer 
- Global, the settings we apply here apply to all repositories of the current user 
- Local, the settings apply to the current repository or the repository in the current folder. We can have different settings for different repositories or different projects 

## Getting help

Here is the way I can get help on "config" command: 

- git config --help (space goes to the next page and q to exit)
- git config -h (short, sweet and a quick refresher help, which gives a short summary of the command, config in this case, and its options) 

## Git cheat sheet

| Creating Snapshots |  |  |
| -------- | -------- | -------- |
| Job description | Git command | Comment |
| -------- | -------- | -------- |
| Creating Snapshots | git init |  |
| Row 2, Column 1 | Row 2, Column 2 | Row 2, Column 3 |
| Row 3, Column 1 | Row 3, Column 2 | Row 3, Column 3 |



### Creating Snapshots
- Initializing a repository **git init**
- Staging files **git add file1.js** # Stages a single file
**git add file1.js file2.js** # Stages multiple files
**git add *.js** # Stages with a pattern
**git add .** # Stages the current directory and all its content

Viewing the status
git status # Full status
git status -s # Short status
Committing the staged files
git commit -m “Message” # Commits with a one-line message
git commit # Opens the default editor to type a long message
Skipping the staging area
git commit -am “Message”
Removing files
git rm file1.js # Removes from working directory and staging area
git rm --cached file1.js # Removes from staging area only
Renaming or moving files
git mv file1.js file1.txt

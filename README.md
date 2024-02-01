# Git

This repository documents my understanding of Git. The followings are my notes from the course **<a href="https://codewithmosh.com/p/the-ultimate-git-course">The Ultimate Git Mastery</a>**

# Table of content

1. [Git Fundamental and Intro](#1) 
    1. [What Git is and why it is so popular](#2)
    2. [How to use Git](#3)
    3. [Git Configuration](#4)
    4. [Getting Help](#5)
    5. [Git Cheat Sheet](#6)
2. [Creating Snapshots](#7)
    1. [Introduction](#8)
    2. [Initializing a Repository](#9)
    3. [Git Workflow](#10)
    4. [Staging Files](#11)
    5. [Committing Changes](#12)
    6. [Committing Best Practices](#13)
    7. [Skipping the staging area](#14)
    8. [Removing files](#15)
    9. [Renaming or moving files](#16)
    10. [Ignoring Files](#17)
    11. [Short Status](#18)
    12. [Viewing Staged and Unstaged Changes](#19)
    13. [Visual Diff Tools](#20)
    14. [Viewing the History](#21)
    15. [Viewing a Commit](#22)
    16. [Unstaging Files](#23)
    17. [Discarding Local Changes](#24)
    18. [Restoring a File to an Earlier Version](#25)
    19. [Creating Snapshots with VSCode](#26)
    20. [Creating Snapshots with GitKraken](#27)
3. [Browsing History](#28)
    1. [Introduction](#29)
    2. [Getting a Repository](#30)
    3. [Viewing the History](#31)
    4. [Filtering the History](#32)
    5. [Formatting the Log Output](#33)
    6. [Aliases](#34)
    7. [Viewing a Commit](#35)
    8. [Viewing the Changes Across Commits](#36)
    9. [Checking Out a Commit](#37)
    10. [Finding Bugs Using Bisect](#38)
    11. [Finding Contributors Using Shortlog](#39)
    12. [Viewing the History of a File](#40)
    13. [Restoring a Deleting File](#41)
    14. [Finding the Author of Line Using Blame](#42)
    15. [Tagging](#43)
    16. [Browsing History Using VSCode](#44)
    17. [Browsing the History Using GitKraken](#45)
4. [Branching](#46)
   1. [Introduction](#47)
   2. [What are Branches](#48)
   3. [Getting a Repository](#49)
   4. [Working with Branches](#50)
   5. [Comparing Branches](#51)
   6. [Stashing](#52)
   7. [Merging](#53)
   8. [Fast-forward Merges](#54)
   9. [3-way Merges](#55)
   10. [Viewing Merged and Unmerged Branches](#56)
   11. [Merge Conflicts](#57)
   12. [Graphical Merge Tools](#58)
   13. [Aborting a Merge](#59)
   14. [Undoing a Faulty Merge](#60)
   15. [Squash Merging](#61)
   16. [Rebasing](#62)
   17. [Cherry Picking](#63)
   18. [Picking a File from Another Branch](#64)
   19. [Branching in VSCode](#65)
   20. [Branching in GitKraken](#66)
5. [Collaboration](#67)
   1. [Introduction](#68)
   2. [Workflows](#69)
   3. [Creating a GitHub Repository](#70)
   4. [Adding Collaborators](#71)
   5. [Cloning a Repository](#72)
   6. [Fetching](#73)
   7. [Pulling](#74)
   8. [Pushing](#75)
   9. [Storing Credentials](#76)
   10. [Sharing Tags](#77)
   11. [Releases](#78)
   12. [Sharing Branches](#79)
   13. [Collaboration Workflow](#80)
   14. [Pull Requests](#81)
   15. [Resolving Conflicts](#82)
   16. [Issues](#83)
   17. [Labels](#84)
   18. [Milestones](#85)
   19. [Contributing to Open-source Projects](#86)
   20. [Keeping a Forked Repository Up to Date](#87)
   21. [Collaboration Using VSCode](#89)
   22. [Collaboration Using GitKraken](#90)
6. [Rewriting History](#91)
   1. [Introduction](#92)
   2. [Why Rewrite History](#93)
   3. [The Golden Rule of Rewriting History](#94)
   4. [Example of a Bad History](#95)
   5. [Undoing Commits](#96)
   6. [Reverting Commits](#97)
   7. [Recovering Lost Commits](#98)
   8. [Amending the Last Commit](#99)
   9. [Amending an Earlier Commit](#100)
   10. [Dropping Commits](#101)
   11. [Rewording Commit Messages](#102)
   12. [Reordering Commits](#103)
   13. [Squashing Commits](#104)
   14. [Splitting a Commit](#105)
   15. [Rewriting History Using GitKraken](#106)

<a name="1"></a>
## Git Fundamental and Intro

<a name="2"></a>
### What is Git and why is it so popular?

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

<a name="3"></a>
### How to use Git

- Command line (the fastest and easiest way to get the job done) 
- Code editors and IDEs
- Graphical User Interfaces built specifically for using Git, **GitKraken Git GUI** is Mosh’s favorite GUI for Git it is free for open source projects but for the commercial projects we have to pay annual fee

In this course we mostly use command line because:
- GUI tools have limitations, so you NEED to roll up your sleeves and use command line sometimes
- GUI tools are **not always available BUT command line is always available**. You may connect to a **server remotely and you may not have permission to install a GUI tool and in these situations, if you don’t know how to use the command line you are in trouble**

The best practice is know how to use Git using command line and use both approaches: using command line and GUI tool. There are times which makes sense using a GUI tool and not a command line but other times using a command line is faster and easier. In summary we should use the right tool for the job. So we use mostly command line except some times when using a GUI tool makes a better sense. 

Git bash (born against shell) emulates the Unix/Linux environment in Windows. 

<a name="4"></a>
### Git configuration 

The first time we need to set up some settings like:
- Name
- Email
- Default editor
- Line ending, very important one 

We can specify these settings at three different levels:

- System, at the very top level the settings we apply here apply to all users of the current computer 
- Global, the settings we apply here apply to all repositories of the current user 
- Local, the settings apply to the current repository or the repository in the current folder. We can have different settings for different repositories or different projects 


        git config --global user.name "Danial Arab"
        git config --global user.email danial.arab@trulioo.com
        git config --global core.editor "code --wait" # with the wait flag we tell the terminal window to wait until we close the new vs code instance
        git config --global core.autocrlf input # crlf = carriage return line feed, for mac/Linux ---> input for windows ---> true

In different OSs, the end of lines are indicated/marked differently:

![](https://github.com/DanialArab/images/blob/main/Git/end%20of%20lines.png)


all these configuration settings are stored in a text file, we can edit that file using our default editor, vs code:

        git config --global -e # This will open our default editor to edit all the global settings          

<a name="5"></a>
### Getting help

Here is the way I can get help on "config" command: 

- git config --help (space goes to the next page and q to exit)
- git config -h (short, sweet and a quick refresher help, which gives a short summary of the command, config in this case, and its options) 

<a name="6"></a>
### Git cheat sheet



| **Creating Snapshots** |  |  |
| -------- | -------- | -------- |
| Initializing a repository | git init |  |
| Staging files | git add file1.js | Stages a single file |
|   | git add file1.js file2.js | Stages multiple files |
|  | git add *.js | Stages with a pattern |
|  | git add . | Stages the current directory and all its content |
| Viewing the status |  |  |



<a name="7"></a>
## Creating Snapshots

<a name="8"></a>
### Introduction

The first thing to know to be able to use Git effectively is **creating snapshots** of your project. 

<a name="9"></a>
### Initializing a Git Repository

Some points on how to initialize a git repo:

+ First we create a directory for our project, which could be anywhere on our machine. 

+ I can create a git repository using **git init**

+ To open a .git: in the Git Bash terminal I need to type explorer .git and press enter (in my ubuntu/wsl it would be explorer.exe .git), the files/folders that I find there in my git directory or repository are **config, HEAD, hooks, info, etc.** this is where Git stores information about my project’s history, I do NOT need to understand these details and structures because these are purely implementation details. It is how Git stores information it is none of our business:) That is why this .git directory is hidden so that we don’t touch it. If we corrupt or remove this directory we will lose our project’s history. 

+ In Windows I can install posh-git to make thing pretty, it is completely optional. For my ubuntu/wsl I installed zsh. 

<a name="10"></a>
### Git Workflow

We have a project directory in which we have a hidden subdirectory i.e., our .git repository. As part of our every day tasks we modify more and more files in our project directory, when our project reaches a state that we want to record we commit those changes into our repository. **Creating a commit is like taking a snapshot of our project**. In Git we have a special area called **staging area or index**, which does not exist in most other version control systems, we essentially propose what we want for the next commit or snapshot. 

When we are done making changes in our file in project directory we add them into the staging area for review and if everything is good then we make a commit then the snapshot will be permanently stored in our repository. So **staging area allows us to review our work before recording a snapshot.** If some of the changes should not be recorded as part of the next snapshot we can **un-stage them and commit them as part of another snapshot.**

Some points:

+ We use add command to add the files to the staging area like git add file1 file2 
+ We use the commit command to permanently store the snapshots in our repository like git commit –m “initial commit” as part of this we supply a meaningful message, initial commit in this example, to indicate what this snapshot represents this is essential for having a useful history (tips: 1- the dash m in the commit command is for message 2- if we have space in the message we need to have a double quote)
+ As we fix bugs, implement new features, and refactor our code we make commit and each commit clearly explains the state of the project at that point in time 
+	A common misconception about Git is that once we commit the changes the staging area becomes empty, which is not correct. After making a commit we still have the same snapshot as we stored in the repository so this staging area is very similar to the staging environment we use when releasing software to production. 
+ If we no longer need a file like file2 we can delete it from our project directory but this file is still in the staging area so once again we use **add command to stage the change**, which is in this case a deletion like **git add file2** here even though we use add command Git knows that file2 is actually deleted so it will delete this file from the staging area or the next snapshot

**Each commit has:**

+ ID, a unique identifier that is generated by Git it is like a revision number 
+ Each commit also has the following information
  + Message
  + Date/time
  + Author
  + Complete snapshot 

These are info about what was changed by who when as well as a complete snapshot of the project at the time it was created so unlike many other version control systems Git does not store deltas or what was changed, it stores the full content, with this we can quickly restore the project to an earlier snapshot without having to compute the changes 

**Question: is it waste of a lot of space when saving the full content in every snapshot?** NO, b/c Git is very efficient in data storage
+ it compresses the content and 
+	does not store the duplicate contents 

you don’t need to know how Git stores data since it is implementation detail and may even change in the future what you need to know is that **each commit contains a complete snapshot of our project and this allows us to quickly get back to the previous state.**

<a name="11"></a>
### Staging Files

Let's write something into two files:

    echo hello > file1.txt 
    echo hello > file2.txt 

git status

    On branch master

    No commits yet

    Untracked files:
      (use "git add <file>..." to include in what will be committed)
            file1.txt
            file2.txt

The two files are in red to indicate they are not in the staging area yet, to add them to the staging area we use **git add** command we can add multiple files separated by **space**, we also can use pattern like git add *.txt to add all the files with txt extension. We can also add the entire directory recursively using **git add .** but be careful b/c there are times that we don’t want to add **large binary files or log files to repository b/c they increase the size of the repository**, we will learn how to ignore these files later in this section. Just remember **git add .** add the entire directory recursively. Let's add the files into the staging area:

    git add .

    git status
    On branch master

    No commits yet

    Changes to be committed:
      (use "git rm --cached <file>..." to unstage)
            new file:   file1.txt
            new file:   file2.txt

Now the two files are in green meaning they are in the staging area. If I modify file1 like

    echo world >> file1.txt

    git status

    On branch master

    No commits yet

    Changes to be committed:
      (use "git rm --cached <file>..." to unstage)
            new file:   file1.txt
            new file:   file2.txt

    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   file1.txt

Now, here we have two files in the staging area b/c they are in green, and we also have one modified file in our working directory now we have the first version of this file1 in the staging area but we changed it after adding it to the staging area so what we have in the working directory is the second version of this file, there are changes that are not staged yet so 

    git add file1.txt
    
    git status
    On branch master

    No commits yet

    Changes to be committed:
      (use "git rm --cached <file>..." to unstage)
            new file:   file1.txt
            new file:   file2.txt

Now we have both files in the staging area without having any un-staged changes. Next we see how to commit a snapshot to permanently sore it in the repository. 

<a name="12"></a>
### Committing Changes

Now we have a snapshot in the staging area which is ready to be permanently stored in the repository:

    git commit -m "initial commit."

In case you want to add more details in the message (more than just “initial commit”, which is pretty useful to you and your coworkers), we just drop the message:

    git commit

When we press enter it opens up the default editor to open the following file name COMMIT_EDITMSG, which is stored in our git subdirectory: 

On the top we can add a short description, which should ideally be less than 80 characters, then we add a line break and after that we can add a long description:

    Initial commit.

    This is our first commit. 
    # Please enter the commit message for your changes. Lines starting
    # with '#' will be ignored, and an empty message aborts the commit.
    #
    # On branch master
    #
    # Initial commit
    #
    # Changes to be committed:
    #   new file:   file1.txt
    #   new file:   file2.txt
    #

After saving changes we close this file in the VS Code. Back to the terminal:

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/desktop/Moon (master)
    $ git commit
    [master (root-commit) 1d36677]  Initial commit.
     2 files changed, 3 insertions(+)
     create mode 100644 file1.txt
     create mode 100644 file2.txt

we had three insertion: 2 in file1 hello world and 1 in file2. Now what we have in our working directory is exactly the same content as we have in our staging area which is exactly the same content as we have in the last commit. 

<a name="13"></a>
###  Committing Best Practices

+ Commit size matters, your commit should not be too big or too small. 
+ The whole point of committing is to record check points as we go so it does not make sense to commit after three days of coding! We want always go back and recover our code if we screw up. 
+	So try to commit often, we commit often like 5 or 10 times a day but of course it depends on the type of work we do and this is just a number don’t take it as a rule. The best practice is to make a commit when you reach a state that you want to record 
+	Each commit should represent a logically separate chain set so don’t mix things up e.g., if you are fixing a bug and you accidentally find a typo in your code you should not commit both these changes in one commit you should have two separate commits one for bug fix and the other for typo, if you accidentally stage both these two changes you can easily un-stage them, will be discussed later. 
+	Have a habit of meaningful commit messages because all of these messages will be shown in history, if your messages are cryptic they will not be helpful to you and other team members, if you do too many things in one commit it will also be hard to have a meaningful message! 
+	In terms of wording in your commit messages, most people prefer to use present tense like “Fix the bug”, instead of “Fixed the bug” you can choose either but be consistent with other team members

<a name="14"></a>
### Skipping the Staging Area

Do we always have to stage our change before committing them? No, we can skip it **BUT** only do this if you really know what you are doing and you are 100% sure your code and changes don’t need to be reviewed. Just remember 99% of times you should always stage your changes before committing. 

    echo test >> file1.txt

    git status
    On branch master
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   file1.txt

    no changes added to commit (use "git add" and/or "git commit -a")

Here I will not use git add file1.txt to first stage the changes and instead straight I commit the changes like:

    git commit -am “Fixed the bugs that prevented users from signing in”. # here we provide the option -a as all that means we want to commit all the modified files 

I could have done git commit -a -m"Fixed the bugs that prevent users from signing in"

<a name="15"></a>
### Removing files

If we want to delete a file which contains unused code, let’s say I have two files in my working directory and also in my staging area which are both committed:

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ cat file1.txt
    hello
    world
    worldi

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ cat file2.txt
    hello

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git status
    On branch master
    nothing to commit, working tree clean

To remove the file2.txt from the working directory I can do (of course rm is just a standard Linux command and not a git command since it does not start with git): 

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ rm file2.txt

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ ls
    file1.txt

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git status
    On branch master
    Changes not staged for commit:
      (use "git add/rm <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            deleted:    file2.txt
    no changes added to commit (use "git add" and/or "git commit -a")

here file2.txt is deleted from the working directory but **still exists in the staging area**, let me prove:

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git ls-files
    file1.txt
    file2.txt

but we had:

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ ls
    file1.txt

As discussed every time we have changes we have to stage those changes using **add** command, here the change is deletion, to stage this change:

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git add file2.txt

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git ls-files
    file1.txt

so file2.txt is no longer in the staging area. 

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git status
    On branch master
    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            deleted:    file2.txt

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git commit -m "Remove unused code"
    [master bdfea43] Remove unused code
     1 file changed, 1 deletion(-)
     delete mode 100644 file2.txt

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git status
    On branch master
    nothing to commit, working tree clean

So remember to remove a file, we have to remove it both from our working directory and also from the staging area. Because it is a very common operation git gives us a command, **git rm**, which performs both steps (i.e., removing the file from the working directory and also from the staging area) in one go (but we still need to commit changes): 

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git rm file2.txt

<a name="16"></a>
### Renaming or moving files

Obvious Reminder: mv is a Linux command for moving and renaming files.

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ ls
    file1.txt

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ mv file1.txt main.py

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git status
    On branch master
    Changes not staged for commit:
      (use "git add/rm <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            deleted:    file1.txt

    Untracked files:
      (use "git add <file>..." to include in what will be committed)
            main.py

    no changes added to commit (use "git add" and/or "git commit -a")

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git add file1.txt

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git add main.py
    warning: in the working copy of 'main.py', LF will be replaced by CRLF the next time Git touches it

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git status
    On branch master
    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            renamed:    file1.txt -> main.py


**indicated in green which means that this is in staging area.**
  
Renaming or moving files is a two-step operation: 
  
+ 1. First we have to modify our working directory 
+ 2. Then we have to stage two types of changes: a deletion and an addition 
  
Similar to removing files git gives us a special command, **git mv main.py main.js**, for renaming and moving files:
  
    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git mv main.py main.js

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git status
    On branch master
    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            renamed:    file1.txt -> main.js

When using git mv main.py main.js changes are applied to both working directory and staging area. 

    dania@DESKTOP-IQ7H5F1 MINGW64 ~/Desktop/Moon (master)
    $ git commit -m "Refactor code."
    [master 4096ae7] Refactor code.
     1 file changed, 0 insertions(+), 0 deletions(-)
     rename file1.txt => main.js (100%)

<a name="17"></a>
### Ignoring Files

In almost every project we should tell git to ignore certain files/directories e.g., we don't want to include log files or binary files that get generated as a result of compiling our code, adding these files only increases the size of our repository without adding any values. Every developer can have their own log files. Log files are not something we want to share and synchronize with other team members. 

         mkdir logs
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ ls
        file1.js  logs
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ echo hello > logs/dev.log
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status
        On branch master
        Untracked files:
          (use "git add <file>..." to include in what will be committed)
                logs/

        nothing added to commit but untracked files present (use "git add" to track)
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$

here we do not want to add the logs directory to the staging area because we do not want Git to track this. So we have to create a special file called **.gitignore** (this file does not have a name and just has an extension and it should be in the root of the project) so:

        echo logs/ > .gitignore 

now let's open it using VS Code:

        code .gitignore

in this file we have a single entry as logs/. We can list as many files and directories as we want here like:

        logs/
        main.log
        *.log

now after saving the changes and closing the VS Code, back in the terminal:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status
        On branch master
        Untracked files:
          (use "git add <file>..." to include in what will be committed)
                .gitignore
        
        nothing added to commit but untracked files present (use "git add" to track)

now Git no longer says we have a new directory called logs because it is ignoring it, instead, it says we have a new file called .gitignore. So let's add this file to the staging area: 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git add .gitignore
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git commit -m"Add gitignore"
        [master 80fc387] Add gitignore
         1 file changed, 3 insertions(+)
         create mode 100644 .gitignore

This is how we can ignore files and directories in Git. But remember this works only if we have not already included a file or directory into the repository. In other words, if we accidentally include a file in the repository and then later add it to gitignore, Git will not ignore that. 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ mkdir bin

let's imagine this bin directory contains our compiled source code.

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ ls
        bin  file1.js  logs
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ echo hello > bin/app.bin
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status
        On branch master
        Untracked files:
          (use "git add <file>..." to include in what will be committed)
                bin/
        
        nothing added to commit but untracked files present (use "git add" to track)

now let's assume we accidentally commit this to our repository: 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git add .
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git commit -m"Added bin."
        [master 66a60dc] Added bin.
         1 file changed, 1 insertion(+)
         create mode 100644 bin/app.bin

here the problem is that every time we compile our code Git will say that this bin/app.bin file is changed and we have to stage it and then commit it which does not make sense. Why should we commit this file every time we compile our application? So back to the .igignore file, we add this bin directory as well:

        logs/
        main.log
        *.log
        bin/
 
 then back to the terminal:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status
        On branch master
        Changes not staged for commit:
          (use "git add <file>..." to update what will be committed)
          (use "git restore <file>..." to discard changes in working directory)
                modified:   .gitignore
        
        no changes added to commit (use "git add" and/or "git commit -a")

which shows that we modified .gitignore, let's stage and commit this change:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git add .
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git commit -m"Included bin/ in gitignore"
        [master 5eccbdd] Included bin/ in gitignore
         1 file changed, 2 insertions(+), 1 deletion(-)

here Git will NOT ignore the changes in this directory because it is already tracking this directory. Like if we modify our bin/app.bin file and see that Git still tracks its changes:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ echo helloworld > bin/app.bin
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ cat bin/app.bin
        helloworld
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status
        On branch master
        Changes not staged for commit:
          (use "git add <file>..." to update what will be committed)
          (use "git restore <file>..." to discard changes in working directory)
                modified:   bin/app.bin
        
        no changes added to commit (use "git add" and/or "git commit -a") 

to solve this problem we first need to remove this directory from the staging area. To see our files in the staging area: 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git ls
        -files
        .gitignore
        bin/app.bin
        file1.js

as seen, the bin directory is in the staging area and we should remove it. 

Point: **git rm** removes the file/directory from both the working directory and the staging area, which is not what we want. We do not want to remove the bin/app.bin from the working directory because that is how we launch our application. We want to remove the bin directory ONLY from the staging area: 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git rm -h
        usage: git rm [<options>] [--] <file>...
        
            -n, --dry-run         dry run
            -q, --quiet           do not list removed files
            --cached              only remove from the index
            -f, --force           override the up-to-date check
            -r                    allow recursive removal
            --ignore-unmatch      exit with a zero status even if nothing matched
            --sparse              allow updating entries outside of the sparse-checkout cone
            --pathspec-from-file <file>
                                  read pathspec from file
            --pathspec-file-nul   with --pathspec-from-file, pathspec elements are separated with NUL character

as seen, --cached option is what we need to only remove files/directories from the index (index is the old term for the staging area, index is used a lot in the Git documentation) so:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git rm --cached -r bin/
        rm 'bin/app.bin'

now this entire directory is removed from the staging area, as is clear:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git ls-files
        .gitignore
        file1.js

now let's run the git status:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status
        On branch master
        Changes to be committed:
          (use "git restore --staged <file>..." to unstage)
                deleted:    bin/app.bin

which shows that this directory is deleted from the staging area. 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git commit -m"Removed the bin directory that was accidentally commited"
        [master 3ad8ae6] Removed the bin directory that was accidentally commited
         1 file changed, 1 deletion(-)
         delete mode 100644 bin/app.bin

 from this point forward Git no longer tracks the changes in this directory. Let's test it:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ echo test >> bin/app.bin
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status
        On branch master
        nothing to commit, working tree clean

at https://github.com/github/gitignore we can find various gitignore templates for different programming languages. For example, for Java we have:

        # Compiled class file
        *.class
        
        # Log file
        *.log
        
        # BlueJ files
        *.ctxt
        
        # Mobile Tools for Java (J2ME)
        .mtj.tmp/
        
        # Package Files #
        *.jar
        *.war
        *.nar
        *.ear
        *.zip
        *.tar.gz
        *.rar
        
        # virtual machine crash logs, see http://www.java.com/en/download/help/error_hotspot.xml
        hs_err_pid*
        replay_pid*

as shown above, for the Java projects it is a great idea to exclude all the class files because these files are automatically generated when we compile the code and so there is no need to include them in the repository. As shown above, we have various patterns like all the class or log files.

<a name="18"></a>
### Short Status

Since the output of the git status is too wordy, very comprehensive though, we may provide the -s flag as an alternative:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ echo sky >> file1.js
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ echo sky > file2.js
        
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status
        On branch master
        Changes not staged for commit:
          (use "git add <file>..." to update what will be committed)
          (use "git restore <file>..." to discard changes in working directory)
                modified:   file1.js
        
        Untracked files:
          (use "git add <file>..." to include in what will be committed)
                file2.js
        
        no changes added to commit (use "git add" and/or "git commit -a")

as seen, we have modified file1.js and also created a new untracked file, file2.js. So alternativel, if we run git status with -s flag w get:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
         M file1.js
        ?? file2.js

**The first, left, column represents the staging area and the right column represents the working directory.** So we have modified file1 and that is why we have a red M in the right column meaning we have some changes here in the working directory that are not yet in the staging area and so that is why we do not have anything in the left column. File2 is a new file and that is why we have 2 question marks in both columns. 

Let's add file1 to the staging area:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git add file1.js
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
        M  file1.js
        ?? file2.js

now for file1, we have a green M in the left/staging area column meaning all the changes we have in the working area are now in the staging area, and in the right column, we do not have anything since we do not have any extra changes. 

When we stage a file Git takes a snapshot of that file and puts it in the staging area so if we modify that file after staging it we have to restage the changes:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ echo ocean >> file1.js
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
        MM file1.js
        ?? file2.js

here in the left column, we have a green M meaning we have some changes in the staging area but also we have some additional changes in the working directory that are not added to the staging area. 


        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git add file1.js
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
        M  file1.js
        ?? file2.js

now all the changes we had in the working directory are now in the staging area. 

now let's add file2 to the staging area:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git add file2.js
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
        M  file1.js
        A  file2.js

now for file2 we have a green A in the left/staging area column, which represents added so file2 is added to the staging area. 

<a name="19"></a>
### Viewing Staged and Unstaged Changes

**Before committing our changes which are in the staging area we need to review our code.** We do not want to commit bad or broken code to our repository. So as the best practice, we always have to first review what we have in the staging area before making a commit. git status command only shows the files that have been affected but how we can see the exact lines of code that we have staged? using the **git diff command**, which gives us what we have in the staging area that goes into the next commit: 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git diff --staged
        diff --git a/file1.js b/file1.js
        index 94954ab..c7bc16c 100644
        --- a/file1.js
        +++ b/file1.js
        @@ -1,2 +1,4 @@
         hello
         world
        +sky
        +ocean
        diff --git a/file2.js b/file2.js
        new file mode 100644
        index 0000000..f5e95e7
        --- /dev/null
        +++ b/file2.js
        @@ -0,0 +1 @@
        +sky

Comparing the files using the terminal is not the best way to do it, we quite often use visual tools, but we need to understand the output of this command for when we do not have access to the visual tools or maybe in the interview you may get asked. 

some points:
+ we are comparing two copies of the same file like a/file1.js b/file1.js
+ **the first copy a/file1.js is the old copy which we have in the last commit**
+ **the second copy, the newer one, is what we currently have in the staging area**
+ Below the files name we have some metadata: index 94954ab..c7bc16c 100644 which does not matter
+  after that we have a legend:
      + changes in the old copy are indicated with a minus sign whereas changes in the new copy are indicated by the plus sign
+ after that we have a header, @@ -1,2 +1,4 @@, with some information about what part of our files were changed:
          we have two segments one is prefixed with - sign giving us info about the old copy like what we had in the last snapshot and the other is prefixed with + sign containing info about the new copy and what we have in the staging area
+ for file2 in the legend, we do not have the old copy, --- /dev/null, because it is an entirely new file and in the last commit we did not have a file called file2

what if we want to see the changes in our working directory that are not staged yet? to do that we run **git diff** without any argument:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git diff

I got nothing as output because I already staged all the changes in the working directory, which can be verified with/;

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
        M  file1.js
        A  file2.js

so if i modify file1 and then run git diff again:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ code file1.js
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
        MM file1.js
        A  file2.js
        

here for file1 we have some changes in the working directory that are not in the staging area.

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git diff
        diff --git a/file1.js b/file1.js
        index c7bc16c..279399c 100644
        --- a/file1.js
        +++ b/file1.js
        @@ -1,3 +1,4 @@
        +hello world
         hello
         world
         sky
         
here **the old copy is what we currently have in the staging area** and **the new copy is what we have in the working directory**. 

to recap **git diff** gives me the unstaged changes and using **git diff --staged** I can see the staged changes that are going into the next commit. Next, we use visual tools to easily compare files. 

<a name="20"></a>
### Visual Diff Tools

There are so many visual diff tools like:
+ KDiff3
+ P4Merge
+ WinMerge (Windows only)
+ VSCode

We will be focusing on VSCode. 

First, we have to tell Git we want to use VSCode as our default difftool through setting two config settings:

        git config --global diff.tool vscode # Through this command we set vscode as our default diff tool 
        git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"  # through this cmd we tell Git how to launch vscode  
        git config --global -e #as mentioned with this command we can edit our global config settings in our default editor  

now back to the terminal instead of using git diff we can use git difftool for comparing files and exactly as before we do not supply any argument we see unstaged changes to compare what we have in the current working directory with what we have in the staging area. And if we want to looka t the staged changes ----> git difftool --staged (exactly the same way as we did with git diff command).

        git difftool

        Viewing (1/1): 'file1.js'
        Launch 'vscode' [Y/n]? y

which gives me back:

![](https://github.com/DanialArab/images/blob/main/Git/difftool_unstaged.png)

to see the staged changes:

        git difftool --staged

        Viewing (1/2): 'file1.js'
        Launch 'vscode' [Y/n]?

![](https://github.com/DanialArab/images/blob/main/Git/difftool_staged1.png)

        Viewing (2/2): 'file2.js'
        Launch 'vscode' [Y/n]? y

![](https://github.com/DanialArab/images/blob/main/Git/difftool_staged2.png)

We do not use difftool so much these days and just for the sake of completeness, it was covered here. These days most editors and IDEs allow us to view the staged and unstaged changes as part of our development environment, as will be discussed later. 

<a name="21"></a>
### Viewing the History

Where are the commits that we make? we can use the git log command to look at our history. 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git log
        commit 3ad8ae60fe280865d8911158f3ebe1109c8bbd57 (HEAD -> master)
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Fri Dec 15 15:37:09 2023 -0800
        
            Removed the bin directory that was accidentally commited
        
        commit 5eccbddb692c433653ff43e79d6e99ae6c6164f5
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Fri Dec 15 15:22:07 2023 -0800
        
            Included bin/ in gitignore
        
        commit 66a60dc6e30be97b2e89322b0e1286c3ea9e49b1
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Fri Dec 15 15:14:52 2023 -0800
        
            Added bin.
        
        commit 80fc387dd323809cac24d547f72fe5024673f477
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Fri Dec 15 15:03:32 2023 -0800
        
            Add gitignore
        :

Here are all the commits we have created sorted from the latest to the earliest: the last commit is on top. To reverse the order:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git log --reverse
        commit b663d4d8b8eda3a23b7e4bdee248cf5fd32cf2b8
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Fri Dec 1 19:47:49 2023 -0800
        
            initial commit
        
        commit 61d84f54480f4cc441b5ad27f274388fa80942cc
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Fri Dec 1 19:49:57 2023 -0800
        
            Fixed the bug in file1
        
        commit 48704fe45441dcb9a14d1016fbe14ad0bf939649
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Fri Dec 1 19:53:51 2023 -0800
        
            Fixed the bug in file2.txt
        
        commit 281f44ccd4a22a91738261d877d097d80ab5f9fa
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Fri Dec 1 19:57:14 2023 -0800
        
            Removed the unused code
        :

each commit has a unique identifier, which is a 40-character hexadecimal string that Git automatically generated for us. It is like a revision number but unlike a revision number does not increase. Next, we have (HEAD -> master): master is the main branch or the main line of work in Git (in some other version control system it is called trunk) in Git we can have multiple branches so we can work on multiple features or multiple bug fixes in parallel and then combine our code. We will discuss these concepts in detail later. HEAD is the reference to the current branch, this is how Git knows what branch we are currently working on. we also have the author's name and email, date, and oneline description. 

we can press space to go to the next page and to quit we can press q.

The log command has a few options one of them is online, which shows us the short summary of commits:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git log --oneline
        3ad8ae6 (HEAD -> master) Removed the bin directory that was accidentally commited
        5eccbdd Included bin/ in gitignore
        66a60dc Added bin.
        80fc387 Add gitignore
        8a5b525 Refactored code
        a7880a3 Removed main.js file
        a1f287b Removed unused code
        440c2bb Initial commit.
        e5c4991 Refactored the code
        0572ce4 Refactored the code
        281f44c Removed the unused code
        48704fe Fixed the bug in file2.txt
        61d84f5 Fixed the bug in file1
        b663d4d initial commit

here we have unique identifiers that are shortened to 7 characters and we only have the oneline description. 

The log command is very powerful and we will use it a lot. We talk about it in a separate section called "browsing history" to discuss various ways to get reports from the history. 

<a name="22"></a>
### Viewing a Commit

If we want to see what exactly has been changed in a given commit we use the show command:

 There are two ways to reference a commit:
 
 + using its unique identifier

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git log --oneline
        3ad8ae6 (HEAD -> master) Removed the bin directory that was accidentally commited
        5eccbdd Included bin/ in gitignore
        66a60dc Added bin.
        80fc387 Add gitignore
        8a5b525 Refactored code
        a7880a3 Removed main.js file
        a1f287b Removed unused code
        440c2bb Initial commit.
        e5c4991 Refactored the code
        0572ce4 Refactored the code
        281f44c Removed the unused code
        48704fe Fixed the bug in file2.txt
        61d84f5 Fixed the bug in file1
        b663d4d initial commit
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git show 66a60dc
        commit 66a60dc6e30be97b2e89322b0e1286c3ea9e49b1
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Fri Dec 15 15:14:52 2023 -0800
        
            Added bin.
        
        diff --git a/bin/app.bin b/bin/app.bin
        new file mode 100644
        index 0000000..ce01362
        --- /dev/null
        +++ b/bin/app.bin
        @@ -0,0 +1 @@
        +hello

 + using a HEAD pointer: as shown in the output of git log --oneline above the HEAD pointer is in front of the last commit so to view the last commit:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git show HEAD
        commit 3ad8ae60fe280865d8911158f3ebe1109c8bbd57 (HEAD -> master)
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Fri Dec 15 15:37:09 2023 -0800
        
            Removed the bin directory that was accidentally commited
        
        diff --git a/bin/app.bin b/bin/app.bin
        deleted file mode 100644
        index ce01362..0000000
        --- a/bin/app.bin
        +++ /dev/null
        @@ -1 +0,0 @@
        -hello

To view the previous commits, we have to use ~ after HEAD and then specify how many steps we want to go back:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git show HEAD~1
        commit 5eccbddb692c433653ff43e79d6e99ae6c6164f5
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Fri Dec 15 15:22:07 2023 -0800
        
            Included bin/ in gitignore
        
        diff --git a/.gitignore b/.gitignore
        index 8432ad3..1dcc30c 100644
        --- a/.gitignore
        +++ b/.gitignore
        @@ -1,3 +1,4 @@
         logs/
         main.log
        -*.log
        \ No newline at end of file
        +*.log
        +bin/
        \ No newline at end of file

if we want to see the exact final version that is stored in the commit and not the differences: we need to provide the full path to the file after the colon like 

        git show HEAD~1: .gitignore 
        
or if the file is in  a subdirectory we have to do 

        git show HEAD~1: bin/app.bin

so:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git s
        how HEAD~1:.gitignore
        logs/
        main.log
        *.log
        bin/

each commit contains a complete snapshot of our working directory and NOT just changes but **when we run the show command we only see the differences i.e., what is changed**, what if we want to see all the files and directories in a commit? using **git ls-tree** command: a tree is a data structure to represent hierarchical information, in trees we have nodes and nodes can have children. A directory in a file system can be represented using a tree and children can be files or other subdirectories. 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git ls-tree HEAD~1
        100644 blob 1dcc30c4cd47f8915741af2cfef91e16e0dc7d89    .gitignore
        040000 tree 64629cd51ef4a65a9d9cb9e656e1f46e07e1357f    bin
        100644 blob 94954abda49de8615a048f8d2e64b5de848e27a1    file1.js

these are all files and directories stored in this commit. Each file or directory has a unique identifier that is generated based on the content of the files. So in the Git database, we have objects with these IDs. As shown above, each object has a type: files are represented using blobs and directories are represented using trees. All of these are objects that are stored in the Git database. And using the show command we can easily view an object in the Git database. 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git ls-tree HEAD~1
        100644 blob 1dcc30c4cd47f8915741af2cfef91e16e0dc7d89    .gitignore
        040000 tree 64629cd51ef4a65a9d9cb9e656e1f46e07e1357f    bin
        100644 blob 94954abda49de8615a048f8d2e64b5de848e27a1    file1.js
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git show 1dcc
        logs/
        main.log
        *.log
        bin/

**So using the show commands we can see the objects in the Git database, these objects can be:**

+ **commits**
+ **blobs (files)**
+ **trees (directories)**
+ **tags, will be discussed later**

  
<a name="23"></a>
### Unstaging Files

We should always review the stuff we have in the staging area before making a commit. 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
        MM file1.js
        A  file2.js

if we decide that what we have for file1.js should not go to the next commit we have to un-stage them (undo the add operation we did before): we use **git restore** command to restore files in different environments like in the working directory or in the staging area. 

to restore file1 in the staging area:

        git restore --staged file1.js # we can have multiple files or patterns like *.js or just a period to restore everything in the staging area 

so

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git restore --staged file1.js
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
         M file1.js
        A  file2.js

now all the changes we had for file1.js in the staging area are now in the working directory. It is essential to understand how the restore command works: **restore command takes the copy from the next (I think before would be the better term) environment: in the case of the staging environment the next environment would be the last commit what we have in the repository so when we restore file1 in the staging area Git took the last copy of this file from the last snapshot and put it in the staging area.**

Now for file2, because we have A for it, it means that it is a new file, so we have this new file in the staging area but this file does not exist in the last commit. So when we restore this file because we do not have a copy of this file in our repository or in our last commit Git will remove this file from the staging area and takes it back to its previous state which is a new untracked file:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
         M file1.js
        A  file2.js
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git restore --staged file2.js
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
         M file1.js
        ?? file2.js


<a name="24"></a>
### Discarding Local Changes

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
         M file1.js
        ?? file2.js

There are times that we have some codes in our working directory that we want to throw away, we can discard local changes using git restore:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git restore .
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s
        ?? file2.js

as seen file2 is still there, it is because file2 is a new untracked file so Git has not been tracking it, when we tell Git to restore this file Git does not know where to get the previous version of this file, it does not exist in our staging environment or in our repository so to remove all new untracked files we need to use git clean command:

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git clean
        fatal: clean.requireForce defaults to true and neither -i, -n, nor -f given; refusing to clean

we got the fatal error with which Git warns me that this is a dangerous operation and if you accidentally remove the untracked file there would be no way to recover them. 

        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git clean -h
        usage: git clean [-d] [-f] [-i] [-n] [-q] [-e <pattern>] [-x | -X] [--] <paths>...
        
            -q, --quiet           do not print names of files removed
            -n, --dry-run         dry run
            -f, --force           force
            -i, --interactive     interactive cleaning
            -d                    remove whole directories
            -e, --exclude <pattern>
                                  add <pattern> to ignore rules
            -x                    remove ignored files, too
            -X                    remove only ignored files

quite often we do git clean -fd 


        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git clean -fd
        Removing file2.js
        (base) danial@LYVR-G6423233FB:/mnt/c/Users/danial.arab/Desktop/git-course/Moon$ git status -s

now file2 is gone and this is how we undo local changes. 

<a name="25"></a>
### Restoring a File to an Earlier Version

 Once Git tracks a file it stores every version of that file in its database so if we screw things up we can always restore a file or directory to a previous version. So let's delete a file deliberately and then restore it:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Moon   master  ls
        bin  file1.js  logs
         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Moon   master  git rm file1.js
        rm 'file1.js'
         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Moon   master ✚  git status -s
        D  file1.js
         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Moon   master ✚  git commit -m"Deleted file1.js"
        [master 2b197b9] Deleted file1.js
         1 file changed, 2 deletions(-)
         delete mode 100644 file1.js
 
in this case we have two ways: first, we can undo/revert the last commit, will be discussed later. Or we can restore a file to a previous version:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Moon   master  git log --oneline
        2b197b9 (HEAD -> master) Deleted file1.js
        3ad8ae6 Removed the bin directory that was accidentally commited
        5eccbdd Included bin/ in gitignore
        66a60dc Added bin.
        80fc387 Add gitignore
        8a5b525 Refactored code
        a7880a3 Removed main.js file
        a1f287b Removed unused code
        440c2bb Initial commit.
        e5c4991 Refactored the code
        0572ce4 Refactored the code
        281f44c Removed the unused code
        48704fe Fixed the bug in file2.txt
        61d84f5 Fixed the bug in file1
        b663d4d initial commit
        (END)

so we want to restore file1 to the commit before the last commit i.e., commit with ID of 3ad8ae6. 

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Moon   master  git restore -h
        usage: git restore [<options>] [--source=<branch>] <file>...
        
            -s, --source <tree-ish>
                                  which tree-ish to checkout from
            -S, --staged          restore the index
            -W, --worktree        restore the working tree (default)
            --ignore-unmerged     ignore unmerged entries
            --overlay             use overlay mode
            -q, --quiet           suppress progress reporting
            --recurse-submodules[=<checkout>]
                                  control recursive updating of submodules
            --progress            force progress reporting
            -m, --merge           perform a 3-way merge with the new branch
            --conflict <style>    conflict style (merge or diff3)
            -2, --ours            checkout our version for unmerged files
            -3, --theirs          checkout their version for unmerged files
            -p, --patch           select hunks interactively
            --ignore-skip-worktree-bits
                                  do not limit pathspecs to sparse entries only
            --pathspec-from-file <file>
                                  read pathspec from file
            --pathspec-file-nul   with --pathspec-from-file, pathspec elements are separated with NUL character

as shown git restore gets three types of arguments: we can supply a bunch of options, we can supply a source by default Git restores the file from the next environment or next area like if the file that we want to restore is in the working directory Git restores it from the staging area and if the file is in the staging area Git will restore it from the last snapshot or the last commit. In our case we want to change the default behavior: we want to restore a file from the commit before the last one:

         ✘ danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Moon   master  git restore --source=HEAD~1 file1.js # then we specify the full path to the file 
         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Moon   master  git status -s
        ?? file1.js

now we have a new untracked file. 

<a name="26"></a>
### Creating Snapshots with VSCode

In VS Code on the left side, I have the source control panel where we can see all the changes in our project. What we see here is similar to the output of the status command: 

![](https://github.com/DanialArab/images/blob/main/Git/source%20control%20in%20vs%20code.png)

we can simply stage our files using a plus icon, and also we can unstage them using the minus icon:

![](https://github.com/DanialArab/images/blob/main/Git/staging%20in%20VS%20Code.png)

after reviewing our file we can provide a message and make a commit. Then back to the Explorer panel after clicking on the file and then clicking on the timeline on the bottom left we can see all the commits applied to this file:

![](https://github.com/DanialArab/images/blob/main/Git/timeline%20in%20vscode.png)

we can click on each commit and see the changes. 

![](https://github.com/DanialArab/images/blob/main/Git/timeline%20in%20vscode%202.png)

here by default, we don't have a way to look at the history, and to do that we need to install a plugin, which will be discussed later in the next section. 

<a name="27"></a>
### Creating Snapshots with GitKraken

![](https://github.com/DanialArab/images/blob/main/Git/GitKraken.png)

if we have changed multiple files in different folders, tree view is very helpful. We can also select "View all files" to see all the files in our project at this point and time, if we unchecked this we can only see the changed files and by change here we mean additions, modifications, and deletion. 

![](https://github.com/DanialArab/images/blob/main/Git/GitKraken%202.png)

in the "Diff View" we have different ways to compare changes: 
+ Hunk view: if we are dealing with a large file with a bunch of changes in different parts of this file Hunk view is an easy way to see the changes in each section 
+ Inline view: it is exactly the same as what we get in the terminal
+ Split view: which gives us the before and after code

Split view:

![](https://github.com/DanialArab/images/blob/main/Git/split%20view.png)

Inline view:

![](https://github.com/DanialArab/images/blob/main/Git/inline%20view.png)

Hunk view:

![](https://github.com/DanialArab/images/blob/main/Git/hunk%20view.png)

Now let's make a new commit, GitKraken is just a GUI tool and it is not a code editor so we need to go to VS Code to make any change to our code. Then back to the GitKraken, we have a notification on having a change then after clicking on the "view change":

![](https://github.com/DanialArab/images/blob/main/Git/GitKraken%203.png)


now here we can easily stage the changes and make a commit. So as simple as that we can create a snapshot of our project using GitKraken. 

<a name="28"></a>
## Browsing History

<a name="29"></a>
### Introduction

We look at various ways to browse the history of our project. We will learn:

+ Search for commits (by author, date, message, etc.)
+ view a commit
+ restore our project to an earlier point
+ compare commits
+ view the history of a file
+ find a bad commit that introduced a bug


<a name="30"></a>
### Getting a Repository

Let's get the repo named Venus to be able to follow along with the course. 

<a name="31"></a>
### Viewing the History

Let's delve more into **git log** command. 

we can have additional options in the git log command: 

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline
         
        a642e12 (HEAD -> master) Add header to all pages.
        50db987 Include the first section in TOC.
        555b62e Include the note about committing after staging the changes.
        91f7d40 Explain various ways to stage changes.
        edb3594 First draft of staging changes.
        24e86ee Add command line and GUI tools to the objectives.
        36cd6db Include the command prompt in code sample.
        9b6ebfd Add a header to the page about initializing a repo.
        fa1b75e Include the warning about removing .git directory.
        dad47ed Write the first draft of initializing a repo.
        fb0d184 Define the audience.
        1ebb7a7 Define the objectives.
        ca49180 Initial commit.
        (END)

if we want to see all the files that have been changed in each commit we can use the stat option:


        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline --stat
        
         a642e12 (HEAD -> master) Add header to all pages.
         audience.txt                                    | 4 +++-
         objectives.txt                                  | 1 +
         sections/creating-snapshots/init.txt            | 2 +-
         sections/creating-snapshots/staging-changes.txt | 2 +-
         toc.txt                                         | 2 +-
         5 files changed, 7 insertions(+), 4 deletions(-)
        50db987 Include the first section in TOC.
         toc.txt | 6 +++++-
         1 file changed, 5 insertions(+), 1 deletion(-)
        555b62e Include the note about committing after staging the changes.
         sections/creating-snapshots/staging-changes.txt | 2 ++
         1 file changed, 2 insertions(+)
        91f7d40 Explain various ways to stage changes.
         sections/creating-snapshots/staging-changes.txt | 6 +++++-
         1 file changed, 5 insertions(+), 1 deletion(-)
        edb3594 First draft of staging changes.
         sections/creating-snapshots/staging-changes.txt | 5 +++++
         1 file changed, 5 insertions(+)
        24e86ee Add command line and GUI tools to the objectives.
         objectives.txt | 3 ++-
         1 file changed, 2 insertions(+), 1 deletion(-)
        36cd6db Include the command prompt in code sample.
         sections/creating-snapshots/init.txt | 3 ++-
         1 file changed, 2 insertions(+), 1 deletion(-)
        9b6ebfd Add a header to the page about initializing a repo.
         sections/creating-snapshots/init.txt | 2 ++
         1 file changed, 2 insertions(+)
        fa1b75e Include the warning about removing .git directory.
         sections/creating-snapshots/init.txt | 3 +++
         1 file changed, 3 insertions(+)
        dad47ed Write the first draft of initializing a repo.
         sections/creating-snapshots/init.txt | 3 +++
         1 file changed, 3 insertions(+)
        fb0d184 Define the audience.
         audience.txt | 3 ++-
         1 file changed, 2 insertions(+), 1 deletion(-)
        1ebb7a7 Define the objectives.
         objectives.txt | 5 +++++
         1 file changed, 5 insertions(+)
        ca49180 Initial commit.
         audience.txt   | 1 +
         objectives.txt | 1 +
         sales-page.txt | 1 +
         toc.txt        | 1 +
         4 files changed, 4 insertions(+)
        (END)

to get the full details we can drop the oneline option:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  gi
        t log --stat
        
        commit a642e1229e3cb69be9bf075d9fe5e752e9a17458 (HEAD -> master)
        Author: Moshfegh Hamedani <moshfegh@live.com.au>
        Date:   Tue Aug 18 09:23:19 2020 -0700
        
            Add header to all pages.
        
         audience.txt                                    | 4 +++-
         objectives.txt                                  | 1 +
         sections/creating-snapshots/init.txt            | 2 +-
         sections/creating-snapshots/staging-changes.txt | 2 +-
         toc.txt                                         | 2 +-
         5 files changed, 7 insertions(+), 4 deletions(-)
        
        commit 50db98710ed4330773f1df55b2a177600d523c9e
        Author: Moshfegh Hamedani <moshfegh@live.com.au>
        Date:   Mon Aug 17 14:27:50 2020 -0700
        
            Include the first section in TOC.
        
         toc.txt | 6 +++++-
         1 file changed, 5 insertions(+), 1 deletion(-)
        
        commit 555b62e1ebb92c97fc69910ad0981a7d6dbbf8c6
        Author: Moshfegh Hamedani <moshfegh@live.com.au>
        Date:   Mon Aug 17 14:26:49 2020 -0700
        
            Include the note about committing after staging the changes.
        
         sections/creating-snapshots/staging-changes.txt | 2 ++
         1 file changed, 2 insertions(+)
        
        commit 91f7d40d6d5bbc336a271607a0488216aaf50cd7
        Author: Moshfegh Hamedani <moshfegh@live.com.au>
        Date:   Mon Aug 17 14:25:43 2020 -0700
        
            Explain various ways to stage changes.
        
         sections/creating-snapshots/staging-changes.txt | 6 +++++-
         1 file changed, 5 insertions(+), 1 deletion(-)
        
        commit edb3594bfa5572d81e24b33aa928938e46907275
        Author: Moshfegh Hamedani <moshfegh@live.com.au>
        Date:   Mon Aug 17 14:24:38 2020 -0700
        
            First draft of staging changes.
        
         sections/creating-snapshots/staging-changes.txt | 5 +++++
         1 file changed, 5 insertions(+)
        
        :

what if we want to see the actual chanegs in each commit? we can use the patch option:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline --patch
        
        a642e12 (HEAD -> master) Add header to all pages.
        diff --git a/audience.txt b/audience.txt
        index 6b3f8f5..4cfef55 100644
        --- a/audience.txt
        +++ b/audience.txt
        @@ -1,2 +1,4 @@
        +AUDIENCE
        +
         This course is for anyone who wants to learn Git.
        -No prior experience is required.
        +No prior experience is required.
        \ No newline at end of file
        diff --git a/objectives.txt b/objectives.txt
        index d31b40a..c882718 100644
        --- a/objectives.txt
        +++ b/objectives.txt
        @@ -1,3 +1,4 @@
        +OBJECTIVES
        
         By the end of this course, you'll be able to
         - Create snapshots
        diff --git a/sections/creating-snapshots/init.txt b/sections/creating-snapshots/init.txt
        index 638729e..f63189e 100644
        --- a/sections/creating-snapshots/init.txt
        +++ b/sections/creating-snapshots/init.txt
        @@ -1,5 +1,5 @@
         INITIALIZING A REPOSITORY
        --------------------------
        +
         The first step is to initialize a Git repository.
         To do that run:
        
        diff --git a/sections/creating-snapshots/staging-changes.txt b/sections/creating-snapshots/staging-changes.txt
        index 506a158..ee0ab5c 100644
        --- a/sections/creating-snapshots/staging-changes.txt
        +++ b/sections/creating-snapshots/staging-changes.txt
        @@ -1,5 +1,5 @@
         STAGING CHANGES
        -===============
        +
         To stage the changes, run:
        
         > git add <filename>
        diff --git a/toc.txt b/toc.txt
        index d019492..cc0798f 100644
        --- a/toc.txt
        +++ b/toc.txt
        @@ -1,5 +1,5 @@
        :


<a name="32"></a>
### Filtering the History

to see the last three commits:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  gi
        t log --oneline -3
        
        
        a642e12 (HEAD -> master) Add header to all pages.
        50db987 Include the first section in TOC.
        555b62e Include the note about committing after staging the changes.
        (END)

to filter the history by author:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ± 
        git log --oneline --author="Mosh"
        
        
        a642e12 (HEAD -> master) Add header to all pages.
        50db987 Include the first section in TOC.
        555b62e Include the note about committing after staging the changes.
        91f7d40 Explain various ways to stage changes.
        edb3594 First draft of staging changes.
        24e86ee Add command line and GUI tools to the objectives.
        36cd6db Include the command prompt in code sample.
        9b6ebfd Add a header to the page about initializing a repo.
        fa1b75e Include the warning about removing .git directory.
        dad47ed Write the first draft of initializing a repo.
        fb0d184 Define the audience.
        1ebb7a7 Define the objectives.
        ca49180 Initial commit.
        (END)

we can also filter by dates using before or after options like if we want to see all the commits from August 16, 2020:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline --after="2020-08-16"
        
        a642e12 (HEAD -> master) Add header to all pages.
        50db987 Include the first section in TOC.
        555b62e Include the note about committing after staging the changes.
        91f7d40 Explain various ways to stage changes.
        edb3594 First draft of staging changes.
        24e86ee Add command line and GUI tools to the objectives.
        36cd6db Include the command prompt in code sample.
        9b6ebfd Add a header to the page about initializing a repo.
        fa1b75e Include the warning about removing .git directory.
        dad47ed Write the first draft of initializing a repo.
        fb0d184 Define the audience.
        1ebb7a7 Define the objectives.
        ca49180 Initial commit.
        (END)

or to see all the commits from yesterday:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline --after="yesterday"

or to see all the commits from oen week ago:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline --after="one week ago"

to filter by commit message or subject, like to see all the commits which have the word "GUI" in their message (of course this operation is case sensitive):

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline --grep="GUI"
        
        24e86ee Add command line and GUI tools to the objectives.
        (END)

we can also filter the history by content, let's say we want to find all the commits that have added or removed a function declaration, like to see all the commits that have added or removed the function hello():


        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline -S"hello()"

since in our repository, we don't have any codes but only the plain English, let's find all the commits that have added the word "OBJECTIVES" 

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline -S"OBJECTIVE"
        
        a642e12 (HEAD -> master) Add header to all pages.
        (END)

to see the actual changes in this commit, we can use the patch option: 


        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline -S"OBJECTIVES" --patch
        
        a642e12 (HEAD -> master) Add header to all pages.
        diff --git a/objectives.txt b/objectives.txt
        index d31b40a..c882718 100644
        --- a/objectives.txt
        +++ b/objectives.txt
        @@ -1,3 +1,4 @@
        +OBJECTIVES
        
         By the end of this course, you'll be able to
         - Create snapshots
        (END)

we can also filter the history by a range of commits: we need to have double periods between the hashes of the two commits of interest:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline
        
        a642e12 (HEAD -> master) Add header to all pages.
        50db987 Include the first section in TOC.
        555b62e Include the note about committing after staging the changes.
        91f7d40 Explain various ways to stage changes.
        edb3594 First draft of staging changes.
        24e86ee Add command line and GUI tools to the objectives.
        36cd6db Include the command prompt in code sample.
        9b6ebfd Add a header to the page about initializing a repo.
        fa1b75e Include the warning about removing .git directory.
        dad47ed Write the first draft of initializing a repo.
        fb0d184 Define the audience.
        1ebb7a7 Define the objectives.
        ca49180 Initial commit.
        (END)
        
        
        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline fb0d184..edb3594
        
        edb3594 First draft of staging changes.
        24e86ee Add command line and GUI tools to the objectives.
        36cd6db Include the command prompt in code sample.
        9b6ebfd Add a header to the page about initializing a repo.
        fa1b75e Include the warning about removing .git directory.
        dad47ed Write the first draft of initializing a repo.
        (END)

what if we want to find all the commits that touch a particular file or bunch of files, like to find all the commits that have modified the toc.txt file:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline toc.txt
        
        a642e12 (HEAD -> master) Add header to all pages.
        50db987 Include the first section in TOC.
        ca49180 Initial commit.
        (END)

sometimes based on the name of the file, Git may complain and say hey this name is ambiguous, in those cases, we have to separate the file name from the options like --oneline, to do so, we use double hyphens to separate the file name from the options we use, i.e., --oneline in the following example:


        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline -- toc.txt


note: we only need to use this -- only if Git complains about the file name and its ambiguity. 

if we want to see the actual changes n each of these commits, once again we can use the patch option **however, the patch option should be listed before the file name**. Because if we put it after the file name Git interprets it as a file name

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline --patch -- toc.txt
        
        
        a642e12 (HEAD -> master) Add header to all pages.
        diff --git a/toc.txt b/toc.txt
        index d019492..cc0798f 100644
        --- a/toc.txt
        +++ b/toc.txt
        @@ -1,5 +1,5 @@
         TABLE OF CONTENT
        -================
        +
         Creating Snapshots
           - Initializing a repository
           - Staging changes
        \ No newline at end of file
        50db987 Include the first section in TOC.
        diff --git a/toc.txt b/toc.txt
        index 8b13789..d019492 100644
        --- a/toc.txt
        :


<a name="33"></a>
### Formatting the Log Output

we can easily customize the output of the log command. In the double quotes, we can specify the format string, which can be a combination of plain text and some placeholders that will get replaced by Git to display pieces of information about each commit:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --pretty=format:"hello %an"
        
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        hello Moshfegh Hamedani
        (END)

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --pretty=format:"%an committed %H
        "
        
        Moshfegh Hamedani committed a642e1229e3cb69be9bf075d9fe5e752e9a17458
        Moshfegh Hamedani committed 50db98710ed4330773f1df55b2a177600d523c9e
        Moshfegh Hamedani committed 555b62e1ebb92c97fc69910ad0981a7d6dbbf8c6
        Moshfegh Hamedani committed 91f7d40d6d5bbc336a271607a0488216aaf50cd7
        Moshfegh Hamedani committed edb3594bfa5572d81e24b33aa928938e46907275
        Moshfegh Hamedani committed 24e86ee2f15e47a0d7b51032d2dc5b684b33465a
        Moshfegh Hamedani committed 36cd6db402cfd897810d4cb33d97ac1e9d1ce2d8
        Moshfegh Hamedani committed 9b6ebfdac0e8a775f17418a63f1153ee74078163
        Moshfegh Hamedani committed fa1b75e8d342a4cb507c28d5417ae6a9111ba81a
        Moshfegh Hamedani committed dad47edb45fb6912ecbb9034daca59f0491da1ab
        Moshfegh Hamedani committed fb0d184c7e31cbb00eed45c98ba502e466b60152
        Moshfegh Hamedani committed 1ebb7a701c4e86331cc64fada6ac1057fdf2dcde
        Moshfegh Hamedani committed ca4918083ec471878d58612142572f3367faf5fd


since it is too verbose we can use the lower case h to see the abbreviation:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --pretty=format:"%an committed %h
        "
        
        Moshfegh Hamedani committed a642e12
        Moshfegh Hamedani committed 50db987
        Moshfegh Hamedani committed 555b62e
        Moshfegh Hamedani committed 91f7d40
        Moshfegh Hamedani committed edb3594
        Moshfegh Hamedani committed 24e86ee
        Moshfegh Hamedani committed 36cd6db
        Moshfegh Hamedani committed 9b6ebfd
        Moshfegh Hamedani committed fa1b75e
        Moshfegh Hamedani committed dad47ed
        Moshfegh Hamedani committed fb0d184
        Moshfegh Hamedani committed 1ebb7a7
        Moshfegh Hamedani committed ca49180

the complete list of these placeholders can be found here **<a href="https://git-scm.com/docs/git-log
">Git log documentation</a>**

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --pretty=format:"%an committed %h
         on %cd"
        
         Moshfegh Hamedani committed a642e12 on Tue Aug 18 09:23:19 2020 -0700
        Moshfegh Hamedani committed 50db987 on Mon Aug 17 14:27:50 2020 -0700
        Moshfegh Hamedani committed 555b62e on Mon Aug 17 14:26:49 2020 -0700
        Moshfegh Hamedani committed 91f7d40 on Mon Aug 17 14:25:43 2020 -0700
        Moshfegh Hamedani committed edb3594 on Mon Aug 17 14:24:38 2020 -0700
        Moshfegh Hamedani committed 24e86ee on Mon Aug 17 14:23:52 2020 -0700
        Moshfegh Hamedani committed 36cd6db on Mon Aug 17 14:22:51 2020 -0700
        Moshfegh Hamedani committed 9b6ebfd on Mon Aug 17 14:22:17 2020 -0700
        Moshfegh Hamedani committed fa1b75e on Mon Aug 17 14:21:30 2020 -0700
        Moshfegh Hamedani committed dad47ed on Mon Aug 17 14:20:50 2020 -0700
        Moshfegh Hamedani committed fb0d184 on Mon Aug 17 14:18:09 2020 -0700
        Moshfegh Hamedani committed 1ebb7a7 on Mon Aug 17 14:17:31 2020 -0700
        Moshfegh Hamedani committed ca49180 on Mon Aug 17 14:17:15 2020 -0700

we can also colorize this output like we can display the author name in green: 

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --pretty=format:"%Cgreen%an%Creset committed %h on %cd"
        
        Moshfegh Hamedani  committed a642e12 on Tue Aug 18 09:23:19 2020 -0700
        Moshfegh Hamedani  committed 50db987 on Mon Aug 17 14:27:50 2020 -0700
        Moshfegh Hamedani  committed 555b62e on Mon Aug 17 14:26:49 2020 -0700
        Moshfegh Hamedani  committed 91f7d40 on Mon Aug 17 14:25:43 2020 -0700
        Moshfegh Hamedani  committed edb3594 on Mon Aug 17 14:24:38 2020 -0700
        Moshfegh Hamedani  committed 24e86ee on Mon Aug 17 14:23:52 2020 -0700
        Moshfegh Hamedani  committed 36cd6db on Mon Aug 17 14:22:51 2020 -0700
        Moshfegh Hamedani  committed 9b6ebfd on Mon Aug 17 14:22:17 2020 -0700
        Moshfegh Hamedani  committed fa1b75e on Mon Aug 17 14:21:30 2020 -0700
        Moshfegh Hamedani  committed dad47ed on Mon Aug 17 14:20:50 2020 -0700
        Moshfegh Hamedani  committed fb0d184 on Mon Aug 17 14:18:09 2020 -0700
        Moshfegh Hamedani  committed 1ebb7a7 on Mon Aug 17 14:17:31 2020 -0700
        Moshfegh Hamedani  committed ca49180 on Mon Aug 17 14:17:15 2020 -0700

again we can find various placeholders for changing the colors in the same git documentation link as above. 

next, we see how to create an alias for this long command i.e., git log --pretty=format:"%Cgreen%an%Creset committed %h on %cd".

<a name="34"></a>
### Aliases

here

<a name="35"></a>
### Viewing a Commit

<a name="36"></a>
### Viewing the Changes Across Commits

<a name="37"></a>
### Checking Out a Commit

<a name="38"></a>
### Finding Bugs Using Bisect

<a name="39"></a>
### Finding Contributors Using Shortlog

<a name="40"></a>
### Viewing the History of a File

<a name="41"></a>
### Restoring a Deleting File

<a name="42"></a>
### Finding the Author of Line Using Blame

<a name="43"></a>
### Tagging

<a name="44"></a>
### Browsing History Using VSCode

<a name="45"></a>
### Browsing the History Using GitKraken

<a name="46"></a>
## Branching

<a name="47"></a>
### Introduction

Branching is one of the most important and powerful features of Git, we will learn how to 
+ use branches to **diverge from the main line of development and work on something else in isolation**
+ compare branches to see their differences
+ to merge branches (different merging techniques: fast forward merging, 3-way merging, squash merging, and rebasing)
+ resolve merge conflicts
+  undo a faulty merge
+  use the essential tools (stashing, cherry picking)

what we learn here in this section can totally change the way we develop software. 

<a name="48"></a>
### What are Branches

Branching allows us to diverge from the main line of work and work on something else in isolation. Conceptually, we can think of a branch as a separate isolated workspace. We have our main workspace called master then we can have another workspace for working on a new feature in isolation, while we are developing this new feature our code becomes unstable so we do not want to release the code in this workspace, we continue working here in this branch then when we are done we test our code and after we fix all the bugs we bring the changes in this workspace into the master. This is called merging. Branching allows us to work on different work items without messing up with the main line of work. We keep the main line as stable as possible so we can release it anytime. Also anyone joining our team can start off on a stable code base. That is the idea of branching. 

The way Git manages branches is very different from many other version control systems like subversion. In subversion when we create a new branch subversion takes a copy of our entire working directory and stores it somewhere else and so this operation takes a while and that is why a lot of subversion users hate branching because it is slow and can waste a lot of space. On the other hand, Git branches are super fast and cheap because branching in Git is just a pointer to a commit. So the master branch is just a pointer to the last commit in the main line of work. As we make new commits, Git moves this pointer forward automatically so it knows what is the latest code in the main line of code. The red in the figure below is the snapshot stored in the last commit:

![](https://github.com/DanialArab/images/blob/main/Git/git%20image.png)

when we create a new branch, Git creates a new pointer that can be moved around:

![](https://github.com/DanialArab/images/blob/main/Git/git%20image%202.png)

this pointer is just a tiny file that contains a 40-byte commit ID. That is why creating a branch in Git is blazingly fast. When we switch to the FEATURE branch in this example, and make new commits Git moves this pointer forward, while the master pointer stays where it is, so Git knows the latest code in each branch (in red below):

![](https://github.com/DanialArab/images/blob/main/Git/git%20image%203.png)

when we switch back to master Git takes the snapshot from the commit that master points to and resets our working directory to that snapshot. So we always have a single woking directory.

How does Git know which branch we are currently working on? Using a special pointer called HEAD:

![](https://github.com/DanialArab/images/blob/main/Git/git%20image%204.png)

this pointer is also another tiny file that contains the name of the branch like master when we switch to a different branch Git moves the HEAD pointer around:

![](https://github.com/DanialArab/images/blob/main/Git/git%20image%205.png)

so it updates the tiny file and writes the name of the target branch. This is how Git can track what branch we are currently working on. 

<a name="49"></a>
### Getting a Repository

we will work using the same repo as we worked with in the previous section, i.e., Venus.

<a name="50"></a>
### Working with Branches

Let's say we got a bug report, to fix this bug, first we should create a new branch called let's say bugfix:

to see thelist of branches in the current repo:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git branch
         
        * master
        (END)

to create a new branch:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git branch bugfix

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git branch
         
          bugfix
        * master
        (END)

the asterisk before master branch indicates that we are currently in the master branch. This is also clear in my zsh. This is very helpful because one of the issues a lot of people struggle with is to accidentally commit their code into the wrong branch. Another way to see the current branch is through the command git status:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git status
        On branch master
        Changes not staged for commit:
          (use "git add <file>..." to update what will be committed)
          (use "git restore <file>..." to discard changes in working directory)
                modified:   audience.txt
                modified:   objectives.txt
                modified:   sales-page.txt
                modified:   sections/creating-snapshots/init.txt
                modified:   sections/creating-snapshots/staging-changes.txt
                modified:   toc.txt
        
        no changes added to commit (use "git add" and/or "git commit -a")

So to fix this imaginary bug we first need to change the current branch to bugfix. There are two ways to do this:
+ in the past we used the checkout command but this command had multiple applications which were confusing and so these days we use
+ the new command git switch:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git switch bugfix
        M       audience.txt
        M       objectives.txt
        M       sales-page.txt
        M       sections/creating-snapshots/init.txt
        M       sections/creating-snapshots/staging-changes.txt
        M       toc.txt
        Switched to branch 'bugfix'

now 

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix ±  git branch
         
        * bugfix
          master
        (END)

now as shown we are in the bugfix branch. But we need to be more clear in the name of branches to make it clear what bug we are trying to fix in this branch (this is very helpful because in the future we may have hundreds of bugs to fix so it is better to use a more specific name). To rename this branch:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix ±  git branch -m bugfix bugfix-signup-form

         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix-signup-form ± 

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix-signup-form ±  git branch
         
         * bugfix-signup-form
          master
        (END)

so now let's make some changes in the audience.txt form:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix-signup-form ±  ls
        audience.txt  objectives.txt  sales-page.txt  sections  toc.txt
        
        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix-signup-form ±  code audience.txt

after some changes in the file:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix-signup-form ±  git status
        On branch bugfix-signup-form
        Changes not staged for commit:
          (use "git add <file>..." to update what will be committed)
          (use "git restore <file>..." to discard changes in working directory)
                modified:   audience.txt
        
        no changes added to commit (use "git add" and/or "git commit -a")


        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix-signup-form ±  git add .
        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix-signup-form ✚  git commit -m"Fixed the bug that prevented the users from signing up."
        [bugfix-signup-form f582a7f] Fixed the bug that prevented the users from signing up.
         6 files changed, 2 insertions(+), 3 deletions(-)
         mode change 100644 => 100755 audience.txt
        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix-signup-form  git log --oneline
        
         
        f582a7f (HEAD -> bugfix-signup-form) Fixed the bug that prevented the users from signing up.
        a642e12 (master) Add header to all pages.
        50db987 Include the first section in TOC.
        555b62e Include the note about committing after staging the changes.
        91f7d40 Explain various ways to stage changes.
        edb3594 First draft of staging changes.
        24e86ee Add command line and GUI tools to the objectives.
        36cd6db Include the command prompt in code sample.
        9b6ebfd Add a header to the page about initializing a repo.
        fa1b75e Include the warning about removing .git directory.
        dad47ed Write the first draft of initializing a repo.
        fb0d184 Define the audience.
        1ebb7a7 Define the objectives.
        ca49180 Initial commit.
        (END)

on the top we have HEAD pointing to the bugfix-signup-form branch that means we are currently in the bugfix-signup-form branch. and "Fixed the bug that prevented the users from signing up." is the latest commit in this branch. Below that we have the master branch which is just a pointer to a commit. As seen our master branch is one commit behind the bugfix-signup-form branch, at some point in the future we are going to merge the bugfix-signup-form branch with the master branch to bring the master branch up, will be discussed later. 

The changes we made in the audience.txt file are ONLY visible in the bugfix-signup-form branch so let's open the audience.txt file in this branch:

         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix-signup-form  ls
        audience.txt  objectives.txt  sales-page.txt  sections  toc.txt
         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix-signup-form  code audience.txt
        
        WHO THIS COURSE IS for
        ======================
        This course is for anyone who wants to learn Git. 

so if we switch back to the master branch and open the audience.txt file we have:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   bugfix-signup-form  git switch master
        Switched to branch 'master'
         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  c
        ode audience.txt
        
        AUDIENCE 
        
        This course is for anyone who wants to learn Git. 
        No prior experience is required.

which is the old version of this file. So **branches allow us to work on different tasks in isolation. The codes we have in these branches are isolated at some point we merge them to bring them together**. While we are in the master branch if we look at our log:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline
        
        a642e12 (HEAD -> master) Add header to all pages.
        50db987 Include the first section in TOC.
        555b62e Include the note about committing after staging the changes.
        91f7d40 Explain various ways to stage changes.
        edb3594 First draft of staging changes.
        24e86ee Add command line and GUI tools to the objectives.
        36cd6db Include the command prompt in code sample.
        9b6ebfd Add a header to the page about initializing a repo.
        fa1b75e Include the warning about removing .git directory.
        dad47ed Write the first draft of initializing a repo.
        fb0d184 Define the audience.
        1ebb7a7 Define the objectives.
        ca49180 Initial commit.
        (END)


on the top we see that HEAD is pointing to the master branch and we do not see the bugfix-signup-form branch because bugfix-signup-form is ahead of the master branch and so its commits are not listed here by default. To view the commits across all the branches we use the **all** option:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline --all
        
        f582a7f (bugfix-signup-form) Fixed the bug that prevented the users from signing up.
        a642e12 (HEAD -> master) Add header to all pages.
        50db987 Include the first section in TOC.
        555b62e Include the note about committing after staging the changes.
        91f7d40 Explain various ways to stage changes.
        edb3594 First draft of staging changes.
        24e86ee Add command line and GUI tools to the objectives.
        36cd6db Include the command prompt in code sample.
        9b6ebfd Add a header to the page about initializing a repo.
        fa1b75e Include the warning about removing .git directory.
        dad47ed Write the first draft of initializing a repo.
        fb0d184 Define the audience.
        1ebb7a7 Define the objectives.
        ca49180 Initial commit.
        (END)

now even though we are in the master branch we can see the commits in other branches. At some time in the future when we are done with the bugfix-signup-for branch when we merged it into the master branch we need to delete it:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  g
        it branch -d bugfix-signup-form
        error: The branch 'bugfix-signup-form' is not fully merged.
        If you are sure you want to delete it, run 'git branch -D bugfix-signup-form'.

this error says that the branch you ant to delete is not fully merged we see this error because we have some changes in this branch which are not merged with the master branch. Git by default prevents us from accidentally deleting this branch unless we merge it first, but if we are pretty sure that we do not want the changes in this branch we can force the deletion by using D:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git branch -D bugfix-signup-form

A point from chatgpt: The new branch will start with the same code as the branch you were on when you created your new branch.

<a name="51"></a>
### Comparing Branches

As we commit to our branches we need to know how they diverge from the master. So here we discuss different ways to compare branches: 
+ To see all the commits ----> git log --oneline master..bugfix-signup-form
+ To see all the actual changes and not the list of commits ----> git diff master..bugfix-signup-form
+ To see the name of the files that will be affected after merging ----> git diff --name-only master..bugfix-signup-form OR git diff --name-status master..bugfix-signup-form

to know what commits are coming into master after merging the bugfix-signup-form branch into the master, the following commands means show me **all the commits that are in bugfix-signup-form and NOT in the master:** 

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log master..bugfix-signup-form
        
        commit f582a7ff9a8d2f20ceefc186f2c87a1f7a23d007 (bugfix-signup-form)
        Author: Danial Arab <danial.arab@trulioo.com>
        Date:   Tue Dec 26 03:27:53 2023 -0800
        
            Fixed the bug that prevented the users from signing up.
        (END)

of course, we can make the oneline option to make the output more concise: 

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git log --oneline master..bugfix-signup-form
         
        f582a7f (bugfix-signup-form) Fixed the bug that prevented the users from signing up.
        (END)

what if we want to see the actual changes and not the list of commits: we do **git diff** like:


        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git diff master..bugfix-signup-form
        
        
        diff --git a/audience.txt b/audience.txt
        old mode 100644
        new mode 100755
        index 4cfef55..e8bdbd5
        --- a/audience.txt
        +++ b/audience.txt
        @@ -1,4 +1,3 @@
        -AUDIENCE
        -
        +WHO THIS COURSE IS for
        +======================
         This course is for anyone who wants to learn Git.
        -No prior experience is required.
        \ No newline at end of file
        (END)

so now we know that when we merge the bugfix-signup-form branch into master in the audience.txt file we are going to have thes changes. 

there is a shorter way to write this command, because we are currently in the master branch we may shorten the above command as:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git diff bugfix-signup-form
         
        diff --git a/audience.txt b/audience.txt
        index e8bdbd5..4cfef55 100755
        --- a/audience.txt
        +++ b/audience.txt
        @@ -1,3 +1,4 @@
        -WHO THIS COURSE IS for
        -======================
        +AUDIENCE
        +
         This course is for anyone who wants to learn Git.
        +No prior experience is required.
        \ No newline at end of file
        (END)

this shows the differences between the bugfix-signup-form branch and the current branch which is master.

Sometimes, we do not want to see the changes in terms of the code and instead, we just want to know what files will be affected, to do so we use the option **name-only** or **name-status**:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git diff --name-only master..bugfix-signup-form
         
        audience.txt
        (END)

or

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git diff --name-status master..bugfix-signup-form
        
        M       audience.txt
        (END)

so once we merge the bugfix-signup-form branch into the master the file audience.txt will be modified. 

<a name="52"></a>
### Stashing

When we switch branches, Git resets our working directory to the snapshot stored in the last commit of the target branch. If we have local changes in our working directory that we have not committed yet these changes could get lost. In these situations, Git does not allow us to switch branches. 

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master  nano audience.txt
        
        # I added * to just have a change
        * AUDIENCE
        
        This course is for anyone who wants to learn Git.
        No prior experience is required.
        
        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master ±  git switch bugfix-signup-form
        error: Your local changes to the following files would be overwritten by checkout:
                audience.txt
        Please commit your changes or stash them before you switch branches.
        Aborting

Here is the Git error message "Please commit your changes or stash them before you switch branches.". In this case, I do not want to commit the changes let's say I am in the middle of something and I am not done yet and I just need to quickly switch to the other branch. In these situations, I need to stash the changes. Stashing something means storing it in a safe place. So we store the changes somewhere in our Git repo but this will not be part of our history. To stash the changes:


        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master ±  git stash push -m "New tax rules."
        Saved working directory and index state On master: New tax rules.


Remember: new untracked files are not by default included in your stash. 

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master  echo hello > newfile.txt
         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master  git status -s
        ?? newfile.txt

So if we stash the changes this new untracked file will not be included in the stash by default. To include it we need to use the --all or -a option:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master  git stash push --all -m "New stash."
        Saved working directory and index state On master: New stash.

to view our stashes:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/Venus   master ±  git stash list
        
        stash@{0}: On master: My new stash.
        stash@{1}: On master: New tax rules.
        (END)

each stash has a unique identifier, as shown above. 

Now we can switch to the other branch:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master  git switch bugfix-signup-form
        Switched to branch 'bugfix-signup-form'
         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   bugfix-signup-form 

after we are done with our work in this branch we can get back to the master:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   bugfix-signup-form  git switch master
        Switched to branch 'master'
         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master 

at this point, we may want to apply the changes from one of our stashes to our working directory but before doing so we want to look at those changes and see what lines of code have been modified:


        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master  git stash show stash@{1}
        
         audience.txt | 4 ++--
         1 file changed, 2 insertions(+), 2 deletions(-)
        (END)

we can also make git stash show stash@{1} shorter like git stash show 1

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master  git stash show 1
        
         audience.txt | 4 ++--
         1 file changed, 2 insertions(+), 2 deletions(-)
        (END)

now we know that in stash 1 one file has been changed, which is audience.txt, and as the changes we have two insertions and  2 deletions. So we can go ahead and apply this stash in our working directory: 

         danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master  git stash apply 1
        On branch master
        Changes not staged for commit:
          (use "git add <file>..." to update what will be committed)
          (use "git restore <file>..." to discard changes in working directory)
                modified:   audience.txt
        
        no changes added to commit (use "git add" and/or "git commit -a")
 
when we are done with a stash we want to remove it to clean things up:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master ±  git stash drop 1
        Dropped refs/stash@{1} (4eb8ff357a7786d27e474574ae7ac25ff436ae19)

now

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master ±  git stash list
        
        stash@{0}: On master: New stash.
        (END)


if we do not need this stash anymore we can also drop it like 'git stash drop 0', or to remove all the stashes we can:

        danial@LYVR-G6423233FB  /mnt/c/Users/danial.arab/Desktop/git-course/branching/Venus   master ±  git stash clear

now all the stashes are gone. 

<a name="53"></a>
### Merging

Merging is all about bringing changes from one branch to another. In Git we have two types of merges:
+ Fast-forward merges (it happens when branches have not diverged) 
+ 3-way merges (it happens when branches have diverged) 

**Fast-forward merges:** Let's say we have a master branch with three commits we create a new branch called bugfix, as discussed in Git a branch is just a pointer to a commit. At this point, both master and bugfix are pointing to the same commit. Now we switch to the bugfix branch and make two commits when we are done we need to bring the changes back to the master branch. Now because these branches have not diverged and there is  a direct linear path from bugfix to master all Git has to do to merge the changes is to bring the master pointer forward. This is called a fast-forward merge. 

![](https://github.com/DanialArab/images/blob/main/Git/fast-forward%20merge.png)

Point: in fast-forward merging, we did not have any additional changes in the master branch so we could easily bring the master pointer forward. 

Now after merging that we are done with the bugfix branch, we can simply remove it, which removes the poniter. 

**3-way merge:** Let's say our bugfix branch is 2 commits ahead of the master branch but before we merge it with the master we went back to the master and made additional commit now our branches are diverged. Here we have some changes in the master that do not exist in the bugfix branch. If we run a merge Git cannot move the master pointer forward and have it point to the same commit as the bugfix because otherwise, we lose the latest commit in the master branch. When we run a merge Git creates a new commit that combines the changes from these two branches. This is called a 3-way merge merge because this new commit is based on three different commits: the common ancestor of our branches which includes the before code and the tips of our branches which contain the after code. So Git looks at three different snapshots: the before snapshot and the after snapshots and based on these it will figure out how to combine these changes so it creates a new commt called a **merge commit**. 

![](https://github.com/DanialArab/images/blob/main/Git/three%20way%20merge.png)

<a name="54"></a>
### Fast-forward Merges

here 

<a name="55"></a>
### 3-way Merges

<a name="56"></a>
### Viewing Merged and Unmerged Branches

<a name="57"></a>
### Merge Conflicts

<a name="58"></a>
### Graphical Merge Tools

<a name="59"></a>
### Aborting a Merge

<a name="60"></a>
### Undoing a Faulty Merge

<a name="61"></a>
### Squash Merging

<a name="62"></a>
### Rebasing

<a name="63"></a>
### Cherry Picking

<a name="64"></a>
### Picking a File from Another Branch

<a name="65"></a>
### Branching in VSCode

<a name="66"></a>
### Branching in GitKraken










<a name="67"></a>
## Collaboration

<a name="68"></a>
### Introduction

So far we have learned all the essential tools to manage a personal project, in this section, we learn about various tools we need to master to collaborate with others. We will focus on:
+ Most common collaboration workflows
+ pushing, fetching, and pulling  objects from a remote repository
+ essential collaboration tools on GitHub as the most popular Git hosting platform like pull requests, issues, and milestones
+ Contributing to open-source projects

these tools are super important and we use them every day working in a team. 

<a name="69"></a>
### Workflows

As we discussed Git is a distributed version control system where every developer has a repository on their machine and so they are not dependent on a central server, they can work offline with their local repository. But how can we collaborate with this model? we can synchronize our work directories with eachother but this is often too complex and error-prone. Instead, we can use something called centralized workflow, as depicted below:

![](https://github.com/DanialArab/images/blob/main/Git/centralized%20workflow.png)

as shown above, everyone has their own local repository but there is also a central repository they use to synchronize their work. This is the workflow used in most private teams and close-source projects. But what is the point of this workflow? How is it better than the centralized version control system like subversion? With this model, **we do not have a single point of failure** we can work with our local repository and if the central repository is unavailable for a period of time we can synchronize our work directly, as shown below:

![](https://github.com/DanialArab/images/blob/main/Git/centralized%20workflow%202.png)

Where we should put this central repository so it is accessible to all team members? 
+ Some organizations put this repository on a **private server** on their private network.
+ Others prefer to use **Git hosting services like GitHub, GitLab, GitBucket**, and so on. With all these services we can set up a repository as a private repository so it is only accessible to our team and no one else. Everyone in the team has push access to write to the central repository.

However, we have another workflow for open-source projects called **integration-manager**. In an open-source project, we have one or more maintainers and many contributors, as shown below:

![](https://github.com/DanialArab/images/blob/main/Git/integration-manager%20workflow.png)

The problem is that we do not know these contributors. So we cannot trust them enough to give them push or write access to our repository. Only the maintainers of the project have push access to the project repository. So if we want to contribute to an open-source project, we should first **fork** the project repository to get a copy of this repository in the **cloud**. Next, we clone this repository to get a local copy on our machine. We make a few commits and when we are ready to share our work, we do a push to send our commits to our forked repository, which is on the cloud, next, we send a pull request to the project maintainer this is a feature built into the platforms like GitHub. So the maintainer of the project will get notified then they can pull in our changes, review them and if they are happy then they can merge our work into their local repository and then push the merge changes to the official repository in the cloud. This is called the integration-manager workflow because someone is in charge of integrating changes we cannot push directly to this official repository and that is why we have to fork it to get a copy in the cloud because this repository is in the cloud it is also visible to the maintainer of the project and that is how they can pull in our changes 

<a name="70"></a>
### Creating a GitHub Repository

Pretty basic stuff!

<a name="71"></a>
### Adding Collaborators

Even though our repository is public no one can make a push or write to it, others can see our code and commit history but they cannot push new commits. So if we work in a team we have to add our team members and give them the push access. 

<a name="72"></a>
### Cloning a Repository

here 

<a name="73"></a>
### Fetching

<a name="74"></a>
### Pulling

<a name="75"></a>
### Pushing

<a name="76"></a>
### Storing Credentials

<a name="77"></a>
### Sharing Tags

<a name="78"></a>
### Releases

<a name="79"></a>
### Sharing Branches

<a name="80"></a>
### Collaboration Workflow

<a name="81"></a>
### Pull Requests

<a name="82"></a>
### Resolving Conflicts

<a name="83"></a>
### Issues

<a name="84"></a>
### Labels

<a name="85"></a>
### Milestones

<a name="86"></a>
### Contributing to Open-source Projects

<a name="87"></a>
### Keeping a Forked Repository Up to Date

<a name="88"></a>
### Collaboration Using VSCode

<a name="89"></a>
### Collaboration Using GitKraken


<a name="90"></a>
## Rewriting History

<a name="91"></a>
###

<a name="92"></a>
###

<a name="93"></a>
###

## 6. Git Cheat Sheet

Course: "The Ultimate Git Mastery", instructor: Mosh Hamedani

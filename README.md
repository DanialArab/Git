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
3. [Browsing History](#19)
    1. [Introduction](#20)
    2. [Getting a Repository](#21)
    3. [Viewing the History](#22)
    4. [Filtering the History](#23)
    5. [Formatting the Log Output](#24)
    6. [Aliases](#25)
    7. [Viewing a Commit](#26)
    8. [Viewing the Changes Across Commits](#27)
    9. [Checking Out a Commit](#28)
    10. [Finding Bugs Using Bisect](#29)
    11. [Finding Contributors Using Shortlog](#30)
    12. [Viewing the History of a File](#31)
    13. [Restoring a Deleting File](#32)
    14. [Finding the Author of Line Using Blame](#33)
    15. [Tagging](#34)
    16. [Browsing History Using VSCode](#35)
    17. [Browsing the History Using GitKraken](#36)


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

+ In windows I can install posh-git to make thing pretty, it is completely optional.

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

here 


## 3. Branching

## 4. Collaboration

## 5. Rewriting History


## 6. Git Cheat Sheet

Course: "The Ultimate Git Mastery", instructor: Mosh Hamedani

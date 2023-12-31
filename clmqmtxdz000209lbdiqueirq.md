---
title: "Mastering Git: Basic Techniques and Concepts"
seoTitle: "Git Mastery: Essential Techniques & Concepts"
seoDescription: "Learn Git basics, version control, GitHub integration; master installation, configuration, and key commands for effective collaboration and workflows"
datePublished: Tue Sep 19 2023 18:12:05 GMT+0000 (Coordinated Universal Time)
cuid: clmqmtxdz000209lbdiqueirq
slug: mastering-git-basic-techniques-and-concepts
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/ZV_64LdGoao/upload/d3d68d473e966059a7dbddc59586bcb4.jpeg
tags: software-development, github, git

---

> In this article, I cover the basics of version control systems (VCS), the differences between Git and GitHub, and a step-by-step guide to install, configure, and use Git alongside GitHub for your software projects. Additionally, I discuss best practices for using Git and GitHub to streamline your workflow and improve collaboration.

---

# Introduction

**This article is part of a series called "**[**Bit by Bit**](https://scrappedscript.com/series/bit-by-bit)**", a series devoted to all things programming. Whether you're still a computer science undergrad or the CTO of Apple, there's something for you here.**

**New articles in this series are posted every Tuesday!**

---

# Version Control Systems

![git version control](https://images.unsplash.com/photo-1556075798-4825dfaaf498?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1476&q=80 align="center")

As the name suggests, version control systems (VCS) are systems designed to manage multiple versions of a file.

Utilizing a Version Control System (VCS) in software development is crucial as it enables you to monitor progress made by yourself or teammates, identify and resolve bugs introduced through software updates, restore corrupted files, and accomplish a great deal more.

VCSs have undergone significant evolution over the past fifty years. Before delving into Git, it may be beneficial to comprehend the origins and reasons behind the development of VCSs as this might foster a more profound understanding and appreciation for Git.

## Local VCS

The very first type of VCSs to ever be developed were local VCSs.

A local VCS works by storing all of the versions of a file on your local computer's hard drive.

One of the earliest VCSs to ever be developed was a software called the *Revision Control System* (RCS). RCS included tools for creating local repositories in a working directory, "checking files in" to the repository, automatic assignment of a revision number for each check-in, "checking files out" from the repository, and setting file permissions across different users on the computer.

## Centralized VCS

To allow for sharing of projects across multiple computers, centralized VCSs were created. Centralized VCSs store all of the versions of a file in a database on a centralized server.

Centralized VCSs are still used to this day. One of the most popular centralized VCSs is Subversion. Subversion allows for the option of using Apache's server networking system or a standalone server, versioning of entire directories (unlike local VCSs such as RCS that only version files), enhanced capabilities for renaming versions, and interactive conflict resolution with Subversion's API.

## Distributed VCS

Distributed VCSs upped the ante by allowing users to download entire repositories to their local computer. As opposed to the centralized model where a repository exists on one server, the distributed model enables a repository and all of its history to exist on multiple computers.

Distributed VCSs are the bread and butter of modern software development. Whether working individually, sharing projects academically, or working as part of a team for a large company, distributed VCSs have far more advantages and features compared to local and centralized VCSs.

As you might've guessed already, Git is the most widely used distributed VCS. As such, it's proving more and more important to add Git to your arsenal of skills.

---

# Background of Git

Git's method of storing data revolves around the idea of storing repository data as snapshots of the files over time. Instead of storing data as individual changes to a file, Git encapsulates a snapshot of the entire filesystem each time a file is committed to the filesystem.

Additionally, Git's speed is what sets it apart from other VCSs. Since Git moves the entire repository to your computer, you can work on projects offline. This offline method of collaboration bypasses the need to constantly retrieve data from a centralized server over a network.

Git's workflow is broken down into three states:

* modified (the file has been edited but not included in your project's next commit)
    
* staged (the file has been added to your project's next commit)
    
* committed (file is stored in local database)
    

## CLI vs GUI

While there are graphical user interfaces (GUIs) to use Git, the command line interface (CLI) for Git is the typical interface that's used.

With the CLI, you have access to all of Git's tools/commands, whereas GUIs are usually limited in the range of Git tools that they include.

Additionally, if you're collaborating with other people on a project, using the CLI for Git ensures that there are no differences in Git capabilities between you and anyone on your team.

With that being said, I know that the command line isn't everyone's favorite place to be on their computer, but there's only a small amount of commands necessary to be a "Git Master".

Rest assured, I'll be covering the exact Git commands you'll need to get started.

## Git vs GitHub

![github logo figurine](https://images.unsplash.com/photo-1618401471353-b98afee0b2eb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1488&q=80 align="center")

Git and GitHub are sometimes confused for one or the other.

GitHub is an online platform that allows users to upload Git repositories to GitHub's cloud server.

Additionally, GitHub does have a GUI for certain Git commands, but it isn't the best idea to use GitHub in this manner for reasons that I'll explain later on.

And just as a side note, GitHub isn't the only online platform that allows users to upload Git repositories. Funnily enough, GitLab (the platform that's featured in the cover photo that I chose for this article) is another option for uploading Git repositories.

However, GitLab's platform is geared towards more niche markets (such as DevOps engineers).

Nevertheless, GitHub is widely regarded for its large, online community of users (which reinforces the open-source nature of Git repositories), the ability to easily and safely share repositories with just a URL, and even the option for GitHub to host your front-end websites on their cloud server for free!

GitHub is a very powerful service that is almost always used alongside Git. For that reason, I'm going to be referencing GitHub throughout the rest of this article.

If you don't have a GitHub account yet, you can make one for free over at [github.com](https://github.com/).

As a side note, if you're currently a student, you can sign up for [GitHub's Student Developer Pack](https://education.github.com/pack#offers) for free which includes GitHub Pro while you're a student (a value of $4/month), a bunch of free online courses in software development, and a huge amount of third-party deals and promotions.

---

# Configuring Git

Before being able to use Git, you'll have to install the software on your computer. If you already have Git installed but haven't used it in a while (or at all), then it's a good idea to check for the latest update as I'll show you how to do below.

## Installing Git

### Installation for Linux

1. Open a terminal window
    
2. Update your system's package list to make sure you're getting the newest version of the Git package
    

```bash
sudo apt update
sudo apt upgrade
```

1. Install/Update Git
    

For Debian-based distributions:

```bash
sudo add-apt-repository ppa:git-core/ppa
sudo apt update
sudo apt install git
```

For Red Hat package manager-based distributions:

```bash
sudo dnf install git-all
```

1. Verify you have the latest version (The latest version is 2.42.0 at the time of writing this article)
    

```bash
git --version
```

### Installation for MacOS

1. Open a terminal window
    
    ![macos terminal window](https://cdn.hashnode.com/res/hashnode/image/upload/v1694810221994/53088aaa-ed78-4cce-bea3-89e52c0959c2.png align="center")
    
2. Install Homebrew (this is a package manager for MacOS)
    

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

* You'll be prompted to enter your computer's password so that the installer has root privileges
    
* You'll then be prompted to press the "Return/Enter" key to confirm the installation
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694810576328/d92b6943-5488-40d2-ac38-4512b6685599.png align="center")

* **NOTE: If you have a Mac with Apple's silicon chip, you'll have to add Homebrew to your PATH (regardless of whether or not you have a Mac with an Intel chip or an Apple chip, Homebrew will provide 2 commands for you to enter after installation if you have a Mac with Apple's chip):**
    

```bash
echo 'eval $(/opt/homebrew/bin/brew shellenv)' >> ~/.zprofile
eval $(/opt/homebrew/bin/brew shellenv)
```

1. Install/Update Git
    

```bash
brew install git
```

1. Verify you have the latest version (The latest version is 2.42.0 at the time of writing this article)
    

```bash
git --version
```

### Installation for Windows OS

1. Download the latest 32-bit version of Git at [https://git-scm.com/download/win](https://git-scm.com/download/win)
    
2. Install Git after it's done downloading
    

## Linking Git with GitHub

* Open a terminal window
    
* Configure Git with the email address you used to sign up for GitHub
    

```bash
git config --global user.name "Name"
git config --global user.email "Email used for GitHub account"
```

* Set the default branch to main
    

```bash
git config --global init.defaultBranch main
```

* Set default branch reconciliation to merge
    

```bash
git config --global pull.rebase false
```

* Verify proper Git configuration with your GitHub account email
    

```bash
git config --get user.name
git config --get user.email
```

* **NOTE: For MacOS users, configure Git to ignore .DS\_Store files**
    

```bash
echo .DS_Store >> ~/.gitignore_global
git config --global core.excludesfile ~/.gitignore_global
```

## Creating an SSH key

Secure Shell (or SSH) is a cryptographic network protocol similar to Secure Sockets Layer (or SSL, the cryptographic network protocol that allows for encrypted data transmission between web browsers and servers).

Instead of allowing for encrypted data transmission, SSH allows for a computer to securely execute server commands over a network.

SSH works by using cryptographic keys to authenticate a user's credentials. After the server authenticates you, the server grants you access to the server's operating system (with limited permissions, of course).

Since you'll need to establish a secure, authentic connection with GitHub's cloud-based server, you'll need to create an SSH key.

There are many different algorithms developed to create cryptographic keys, but the Ed25519 algorithm is currently the most secure.

* Open a terminal window
    
* First, check if you already have an Ed25519 key installed on your system
    

```bash
ls ~/.ssh/id_ed25519.pub
```

* If the above command returns "No such file or directory", then enter the following to create an Ed25519 key (**replace "youremail" with the email associated with your GitHub account**)
    

```bash
ssh-keygen -t ed25519 -C youremail
```

* You'll be prompted to select a location to save the key; just hit the "Enter/Return" key to automatically save it to your path
    
* Next, you'll be prompted to generate a password to *use* the key (this password has nothing to do with your computer password or GitHub account password)
    

## Linking SSH key with GitHub

1. Log into [https://github.com/](https://github.com/)
    
2. Click your profile picture in the top right
    
3. Click on "Settings"
    
4. On the lefthand sidebar, click "SSH and GPG Keys"
    
5. Click "New SSH Key"
    
6. Name your key
    
7. Open a terminal window
    
8. Output your SSH key to the console:
    

```bash
cat ~/.ssh/id_ed25519.pub
```

1. Copy the SSH key
    
2. Paste the SSH key to the key field on GitHub
    
3. Verify the key type is set to "Authentication Key"
    
4. Click "Add SSH Key"
    

---

# Git Workflow

Now that you've created your GitHub account, installed Git, and configured Git with GitHub, you're ready to start using Git alongside GitHub to manage your projects.

While there are a lot of Git commands to learn, I'm going to cover only a handful of commands. However, these commands are more than enough to be able to start properly using Git.

After you've learned and integrated these commands into your workflow, you'll be a certified "Git Master" ( unofficially ;) )

## Creating a repository

1. Go to [https://github.com](https://github.com)
    
2. Click the button with the plus-sign icon to the left of your profile picture
    
3. Click "New repository"
    
4. Name the repository in the Repository name input field
    
5. Checkmark "Add a README file"
    
6. Click "Create repository"
    
7. You'll then be automatically redirected to the new repository's page on GitHub
    
8. Click the green "Code" button on the repository's page
    
9. Click the "SSH" button
    
10. Copy the SSH URL
    
11. Open a terminal window
    
12. **OPTIONAL: Create a new directory for your repository**
    

```bash
mkdir WhateverNameYouWant
```

1. If you did Step 12: enter the repository's directory
    

```bash
cd WhateverNameYouChose
```

1. Clone the repository onto your computer
    

```bash
git clone PasteTheSSHURLYouCopiedFromGitHub
```

## Committing files

Now that you've cloned your repository to your computer, you can start creating/adding local files to your repository's folder.

1. From the terminal, enter your repository's folder
    

```bash
cd NameOfRepoOnGitHub
```

1. Create a new file in the folder
    

```bash
touch FileName.FileExtension
```

1. Check the status of your local repository (this should return an output stating that the new file you created is not yet **staged**)
    

```bash
git status
```

1. Add file to staged status
    

```bash
git add FileName.FileExtension
```

1. Commit the file
    

```bash
git commit -m "Type in some generic message"
```

1. Check the log of commits to the repository (this will output a history of commits alongside the name of the person who made the commit, the date and time of the commit, and the message included with the commit)
    

```bash
git log
```

## Opening files

The next task to learn is how to open/modify files from the repository.

1. **OPTIONAL**: From the terminal, open the repository folder in your code editor of choice (<mark>I personally use </mark> [<mark>Visual Studio Code</mark>](https://code.visualstudio.com/)<mark>. Visual Studio Code is a completely free and open-source code editor with a lot of free extensions to code in pretty much any language or library. </mark> **<mark>The "code" command in my example is a command installed with Visual Studio Code; this command will open the entire repository folder in the Visual Studio Code desktop app</mark>**<mark>.</mark>)
    

```bash
code .
```

1. If you didn't do Step 1: Open your chosen code editor --&gt; File --&gt; Open --&gt; Click your repository's folder
    
2. Edit the README.md file (**this is a markdown file that is traditionally used by authors to include a description of the repository and how the repository works; for now, you can just add some generic text into the file**)
    
3. From your terminal, check the status of the repository (**you'll see that Git automatically detects you made changes to README.md but haven't added the file to staging yet**)
    

```bash
git status
```

1. Add README.md to staging
    

```bash
git add README.md
```

1. Commit README.md
    

```bash
git commit -m "Type in a commit message"
```

## Pushing files

You now know how to clone a repository onto your computer, add new files to your local repository, modify existing files in the repository, add files to staging, and commit file changes.

The last piece of the Git and GitHub workflow you'll need to learn is how to upload those changes to GitHub's cloud server so that the entire world can see your wonderful Git repository.

1. From the terminal, push your repository to GitHub (**please keep in mind that whatever new file(s) or file edit(s) you haven't committed in your local repository will NOT be pushed to GitHub**)
    

```bash
git push origin main
```

1. Verify that your local repository was uploaded to GitHub by refreshing your repository's page in the browser (**you should see the new file you created in the previous steps, as well as the edit to README.md**)
    

---

# Best Practices

![software engineer team working on computer](https://images.unsplash.com/photo-1528901166007-3784c7dd3653?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80 align="center")

Beyond just *using* Git and GitHub for your projects, there are some conventions that you should consider implementing.

If you're using Git and GitHub for academic or business purposes, these conventions will make your project's overall workflow much more efficient if you're working as part of a team.

Even if you're only using Git and GitHub for personal purposes, using these conventions will also help to keep your projects organized and prevent you from forgetting why/how you did something.

Consider these conventions analogous to implementing best practices within your code (such as variable naming, comments, appropriate whitespace, etc.).

## Editing files

Whenever you modify a repository, there are 2 important steps to take.

1. Only modify the repository with the Git workflow
    
    * While you can edit code directly on GitHub's website, it is highly advised that you don't do this
        
    * The main reasoning behind this is to not confuse yourself with changes you've made
        
    * Let's say you forgot that you added some function to a program on GitHub; now when you go back at a later time to work on the program in your code editor, you might add some redundant function or an incompatible function with the function you added to the file on GitHub
        
2. Test your edits before committing and pushing
    
    * Don't be so antsy with your Git commits
        
    * Verify that your edits work and accomplish the appropriate goal
        
    * This will save lots of time in the long run and prevent your team from being confused by careless commits
        

## Atomic commits

The idea of atomic commits relates to my last point.

Atomic commits are essentially commits that are for one small edit in your code.

The main idea here is that by only committing one small change at a time, you'll avoid confusion later on if you commit a bunch of edits in your program under one commit and one or more of those edits breaks your program.

Additionally, this will help improve your focus. By sticking to atomic commits, you're forcing yourself to think about the exact reason why you made an edit and what the edit does.

## Commit messages

Commit messages should be as concise and descriptive as possible.

Putting "fixed the factorial method in the Calculator class" as a commit message isn't helpful for you or anyone else.

Include the why and how in your commit messages.

Why did you edit the factorial method in the Calculator class? How did you edit it and test it?

As for the formatting of a commit message, you should put a subject and a body.

### Subject

The subject should be a headline of the edit and should begin with a present-tense verb.

For example: **Include error handling for Calculator factorial method**

### Body

The body should describe the why and how.

For example:

**Program crashes when user enters negative integer.**

**Fix issue by adding condition to check if user enters number less than 0.**

**Prevent program from crashing by raising error to remind user to enter integer greater than or equal to 0 if they enter a negative number.**

---

# Conclusion

Congrats! You now have all the knowledge, tools, and wisdom to start effectively using Git and GitHub for your software projects.

In this article, you learned the basic concepts of 3 VCSs (local, centralized, and distributed), the difference between Git and GitHub, how to install and configure Git, how to streamline your workflow using Git and GitHub, and some best practices for using Git and GitHub.

If this article stimulated you to create your first repository, feel free to post a URL to your GitHub repo in the comment section down below!

Additionally, if you have any lingering questions or suggestions for a topic you want me to cover in the future, feel free to also post those in the comments.

Lastly, make sure to follow my newsletter so that you don't miss out on when I post new content.
---
title: "🚀The Version Control System Empowering Collaboration and Code Management.🚀"
datePublished: Tue Jul 25 2023 17:21:47 GMT+0000 (Coordinated Universal Time)
cuid: clkikdjcv000q09l7eek4eljl
slug: the-version-control-system-empowering-collaboration-and-code-management
tags: github, git, 90daysofdevops, day10, trainwithshubham

---

### 🔴Introduction:

In today's fast-paced and collaborative world of software development, version control systems play a pivotal role in ensuring efficient code management, collaboration, and tracking of changes over time. Among the various version control systems available, Git has emerged as the most popular and widely adopted tool, enabling developers to work together seamlessly on projects of any scale.

### 🔴What is Git?

Git, developed by Linus Torvalds in 2005, is a distributed version control system designed to track changes in code during software development. It provides a robust framework to collaborate with other developers, manage code efficiently, and maintain a detailed history of project modifications. Git's decentralized nature means that each developer maintains their copy of the project's entire history, which fosters a flexible and distributed approach to code collaboration.

**⚠️Key features of Git:⚠️**

* Distributed Nature
    
* Speed and Performance
    
* Branching and Collaboration
    
* Data Integrity
    
* Extensibility
    

### 🔴What is GitHub?

GitHub is a web-based platform built around Git, providing a collaborative environment for developers to host, review, and manage their Git repositories. It enhances Git's capabilities with additional features such as issue tracking, project management, and social networking aspects, making it a central hub for software development teams and open-source communities. Let's dive into the key features and content found on GitHub.

## 🔴What is Version Control? How many types of version controls do we have?

Version control is a system that tracks changes to a file or set of files over time so that you can recall specific versions later. It allows you to revert files to a previous state, revert the entire project to a previous state, compare changes over time, see who last modified something that might be causing a problem, who introduced an issue and when, and more.

There are two main types of version control systems: centralized version control systems and distributed version control systems.

1. A centralized version control system (CVCS) uses a central server to store all the versions of a project's files. Developers "check out" files from the central server, make changes, and then "check-in" the updated files. Examples of CVCS include Subversion and Perforce.
    
2. A distributed version control system (DVCS) allows developers to "clone" an entire repository, including the entire version history of the project. This means that they have a complete local copy of the repository, including all branches and past versions. Developers can work independently and then later merge their changes back into the main repository. Examples of DVCS include Git, Mercurial, and Darcs.
    

## 🔴Why do we use distributed version control over centralized version control?

1. Better collaboration: In a DVCS, every developer has a full copy of the repository, including the entire history of all changes. This makes it easier for developers to work together, as they don't have to constantly communicate with a central server to commit their changes or to see the changes made by others.
    
2. Improved speed: Because developers have a local copy of the repository, they can commit their changes and perform other version control actions faster, as they don't have to communicate with a central server.
    
3. Greater flexibility: With a DVCS, developers can work offline and commit their changes later when they do have an internet connection. They can also choose to share their changes with only a subset of the team, rather than pushing all of their changes to a central server.
    
4. Enhanced security: In a DVCS, the repository history is stored on multiple servers and computers, which makes it more resistant to data loss. If the central server in a CVCS goes down or the repository becomes corrupted, it can be difficult to recover the lost data.
    

Overall, the decentralized nature of a DVCS allows for greater collaboration, flexibility, and security, making it a popular choice for many teams.

✅Follow this URL to install git: [**https://git-scm.com/download/**](https://git-scm.com/download/win)

✅Follow this URL to create a GitHub account: [https://github.com/](https://github.com/)

### ⚠️Three Stages Architecture of Git:⚠️

1. **Working Directory:** The working directory is the first stage of the 3-stage architecture. It is the directory on your local machine where you keep and modify your project files. When you clone a Git repository or create a new one, the files and directories are placed in your working directory.
    
    In this stage, you make changes to your project's files, such as adding new code, modifying existing code, or deleting files. These changes are visible and editable in your local working directory.
    
2. **Staging Area (or Index):** The staging area, also known as the index, is the second stage of the architecture. It acts as a middle ground between the working directory and the repository. When you make changes to your project files in the working directory, you need to explicitly tell Git which changes you want to include in the next commit. This process is called "staging" changes.
    
    Staging is essential because it allows you to control what goes into your commitment. You can choose to include only specific changes or exclude certain files from being part of the next commit. Staging allows you to review your changes before making them a permanent part of the repository.
    
3. **Repository:** The repository is the third and final stage of the architecture. It is where Git permanently stores the history of your project and all the changes made over time. The repository contains a record of all the commits, including their metadata (author, timestamp, commit message) and references to the objects that represent the project's files and directories.
    
    Once you've staged the changes you want to include, you create a new commit. A commit is a snapshot of the changes in the staging area. Each commit is uniquely identified by a commit hash (a long alphanumeric string). Once committed, the changes become a part of the repository's history and are safely stored in the Git repository.
    
    The repository also includes information about branches, tags, and remote repositories if you're collaborating with others.
    

### 🛠️Create a Repository on GitHub:🛠️

To create a repo on GitHub, go to GitHub click on profile pic then click on your repositories and next click on new,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690300940944/5fba50c4-6abe-4e90-91d8-7410776f9ad1.png align="center")

### 🛠️Clone GitHub repo to your local system:🛠️

Open your GitHub repo and click on the code button then copy the repo URL starting with HTTPS,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690301361656/afca5177-6c1e-43e4-95f0-72fa872f359c.png align="center")

To clone your GitHub repo open cmd on your local system, choose the path or directory, where you want to clone the repo. use the following command,

```plaintext
git clone https://github.com/Ghaterishi/GitnGithubTasks.git
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690301530375/d4bcabe7-3e66-43b7-b643-09a6ada2c3a2.png align="center")

### 🛠️Add Remote origin.🛠️

After cloning the repo, open it in vs code and add one sample Txt file in it,

After this add your git remote origin using the following command,

```plaintext
git remote add origin https://github.com/Ghaterishi/GitnGithubTasks.git
git remote -v # check origins
```

### 🛠️Push your files to GitHub from the local system:🛠️

After adding your origin, use the following commands starting with git(in yellow colour) to push your repo,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690302432391/1f67b39d-ccf0-477b-9425-c1ac40ef3a4f.png align="center")

### **🔁Conclusion**:

In this blog, you get a basic understanding of git, GitHub and how its work i encouraged you to go and follow the steps mentioned in the blog so you will understand better.

Thanks for reading..!

Follow me on Hashnode for such amazing content.

📌Linkedin: [www.linkedin.com/in/rushikesh-ghate-525060199](http://www.linkedin.com/in/rushikesh-ghate-525060199)

📌GitHub: [https://github.com/Ghaterishi](https://github.com/Ghaterishi/90daysofDevopsBlogs.git)
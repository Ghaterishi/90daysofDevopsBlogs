---
title: "🚀Advance Git & GitHub for DevOps Engineers.🚀"
datePublished: Fri Jul 28 2023 16:13:55 GMT+0000 (Coordinated Universal Time)
cuid: clkms9t3q000609mrdvhd1w2v
slug: advance-git-github-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690560412694/d016aa4a-e57d-4a85-aff3-2b2749af9767.jpeg
tags: blogging, github, devops, 90daysofdevops, trainwithshubham

---

### **👉What is a Branch**?

If you're working on a project with others. A branch is like a separate copy of the project where you can make changes without affecting the main version.

Using branches in Git allows you to work on different parts of the project simultaneously, collaborate with others more effectively, and keep track of changes in a structured way. It's like having separate workspaces for different tasks, helping you stay organized and making it easier to manage the project as a team.

**📌Creating a Branch**:

```plaintext
git checkout -b <branch_name>
```

**📌Switching Branches**:

When you want to work on a specific branch, you "jump" to that branch so that any changes you make only happen there.

```plaintext
git checkout  <branch_name>
```

**📌Viewing Branches**:

You can see a list of all the different branches available in the project.

```plaintext
git branch
```

**📌Merging Branches**:

When you're done with your changes on a branch, you can combine them back into the main version, so everyone can benefit from your work.

```plaintext
git merge <branch-name>
```

**📌Deleting Branches**:

After merging, you can remove the branch you were working on since its changes are now part of the main version.

```plaintext
git branch -d <branch_name>
```

### 👉What are Git Revert and Git Reset?

**🔴Revert**:

Revert means to undo a specific commit or a series of commits in your project's history without removing them entirely. It's like going back in time to fix a mistake without erasing everything that came after it.

> Undo changes safely, by creating a new commit that undoes the previous one, preserving the history.

**🔴Reset**:

Reset is a more powerful command, and it can be a bit risky if not used carefully. Reset allows you to move the current branch to a specific commit, effectively "rewinding" your project's history to that point.

> Move the project's history back to a specific point, erasing the changes made after that point. Use with caution as it can make you lose work.

### 👉What are Git Merge and Git Rebase?

**🔴Merge**:

In Git, merging is like combining changes from different branches into one branch, creating a new "merge commit." This is useful when you want to bring together changes from different people or features into the main project.

> Combine changes from different branches, creating a new merge commit. It's like merging different branches of the project into one.

**🔴Rebase**:

In Git, it moves your branch's starting point to the end of another branch, incorporating all the changes from the other branch first. This helps keep your history linear and can make it easier to manage changes.

> Move your changes to a new starting point, making it look like you started working from there. It's like taking your work and applying it on top of someone else's changes.

### 🛠️Task:🛠️

Add a text file called version01.txt inside the Devops/Git/ with “This is the first feature of our application” written inside. This should be in a branch coming from `master`, \[hint try `git checkout -b dev`\], switch to the `dev` branch ( Make sure your commit message will reflect as "Added new feature"). \[Hint use your knowledge of creating branches and Git commit command\]

* version01.txt should reflect at the local repo first followed by the Remote repo for review.
    

Add a new commit in `dev` branch after adding the below-mentioned content in Devops/Git/version01.txt: While writing the file make sure you write these lines

* 1st line&gt;&gt; This is the bug fix in the development branch.
    
* 2nd line&gt;&gt; This is gadbad code.
    
* 3rd line&gt;&gt; This feature will gadbad everything from now.
    

Restore the file to a previous version where the content should be “This is the bug fix in the development branch”.

### **✍️Solution:✍️**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690559956451/c73cd710-90f3-49e1-8390-cf1783bb635e.png align="center")

### 🔁Conclusion:

In this blog, we understand some advanced concepts of git and commands. Also, i mentioned one task and its solution. I encouraged you to go ahead and do this task on your own so you will get a better understanding of branches, how to create, how to merge and many more. check your solution is match mine.

🙏Thanks for reading..!

Follow me on Hashnode for such amazing content.

📌Linkedin: [www.linkedin.com/in/rushikesh-ghate-525060199](http://www.linkedin.com/in/rushikesh-ghate-525060199)

📌GitHub: [https://github.com/Ghaterishi](https://github.com/Ghaterishi/90daysofDevopsBlogs.git)
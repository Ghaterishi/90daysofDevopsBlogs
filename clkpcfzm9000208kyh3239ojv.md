---
title: "🚀Advance Git & GitHub for DevOps Engineers: P-2🚀"
datePublished: Sun Jul 30 2023 11:14:08 GMT+0000 (Coordinated Universal Time)
cuid: clkpcfzm9000208kyh3239ojv
slug: advance-git-github-for-devops-engineers-p-2
tags: challenge, github, git, 90daysofdevops, tws

---

### 💥Introduction:💥

In part one we discussed some advanced git commands like git merge, rebase and many more. In this blog, we will discuss git stash, cherry and cherry-picking. So lets get started.

### 👝What is Git stash?👝

You're working on something but need to switch to another task before finishing. Instead of committing half-done work, you want to store your half-work somewhere here git stash comes into the picture. Git Provides some space called a stash to store your half-done work. It's like putting your changes on a shelf(stash) temporarily. let's discuss its commands,

* To store your half-work,(make sure you are on the same branch you are working on)
    

```plaintext
git stash
```

* To restart your half-done work,
    
    ```plaintext
    git stash pop  or git stash apply
    ```
    
    ### 🍒What is Git Cherry?🍒
    

When you work with others and have different branches, it's essential to track unmerged changes. That's where `git cherry` comes in. It gives us the hash id of an unmerged commit of a particular branch.

```plaintext
git cherry <branch_name>
```

### 🍒What is git cherry-pick?🪧

Consider you have done lots of changes in the dev branch and now you want to merge specific commits rather than all commits/changes to the production branch where git cherry-pick comes into the picture. So git cherry-pick gives you the functionality of picking up specific commits of some branch and adding it to another one.

```plaintext
git cherry-pick <commit_hash_id>
```

### 🛠️Task-01.🛠️

* Create a new branch and make some changes to it.
    
* Use git stash to save the changes without committing them.
    
* Switch to a different branch, make some changes and commit them.
    
* Use git stash pop to bring the changes back and apply them on top of the new commits.
    

📌**Solution**:✅

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690712204334/abef117b-a011-4cfa-beac-f66c63a15914.png align="center")

### 🧐Task-02🧐

* In version01.txt of the development branch add the below lines after “This is the bug fix in development branch” that you added in Day10 and reverted to this commit.
    
* Line2&gt;&gt; After bug fixing, this is the new feature with minor alterations”
    
    Commit this with the message “ Added feature2.1 in development branch”
    
* Line3&gt;&gt; This is the advancement of the previous feature
    
    Commit this with the message “ Added feature2.2 in development branch”
    
* Line4&gt;&gt; Feature 2 is completed and ready for release
    
    Commit this with the message “ Feature2 completed”
    
* All these commits messages should be reflected in the Production branch too which will come out from the Master branch (Hint: try rebase).
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690713274547/ad10e393-72f0-46de-8f14-275a58016ddc.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690713305347/abd5f76f-4d69-4cfc-91b3-99f393cb8ea3.png align="center")

### 🎇Task-03:🎇

* In the Production branch Cherry pick Commit “Added feature2.2 in development branch” and added the below lines in it:
    
* The line to be added after Line3&gt;&gt; This is the advancement of the previous feature
    
* Line 4&gt;&gt;Added a few more changes to make it more optimized.
    
* Commit: Optimized the feature.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690714413182/0e3ebbda-e63f-4e73-a5f1-d04338b51446.png align="center")
    

### Resolving Conflicts:

Conflicts can occur when you merge or rebase branches that have diverged, and you need to manually resolve the conflicts before it can proceed with the merge/rebase. git status command shows the files that have conflicts, the git diff command shows the difference between the conflicting versions and the git add command is used to add the resolved files.

### 🔁Conclusion:🔁

👉Git Stash: Save Unfinished Work

👉Git Cherry: Check for Unmerged Changes

👉Git Cherry-Pick: Grab Specific Commits

📌In this blog, we understand some advanced concepts of git and commands. Also, I mentioned some tasks and its solution. intentially i don't mention steps, I encouraged you to go ahead and do this task on your own so you will get a better understanding of branches, how to create, how to merge and many more. check your solution will match mine.

🙏Thanks for reading..!

🤝Follow me on Hashnode for such amazing content.

📌Linkedin: [**www.linkedin.com/in/rushikesh-ghate-525060199**](http://www.linkedin.com/in/rushikesh-ghate-525060199)

📌GitHub: [**https://github.com/Ghaterishi**](https://github.com/Ghaterishi)
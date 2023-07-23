---
title: "🚀Security in Linux.🚀"
datePublished: Thu Jul 20 2023 10:21:59 GMT+0000 (Coordinated Universal Time)
cuid: clkb06e8x000n09jw4wvd66cp
slug: security-in-linux
tags: linux, acl, 90daysofdevops, day6, tws

---

In this Blog, we will try to understand, What is security in Linux and how can we manage it? let's get started..!

### **🖍️Introduction:**

why do we need to secure the files? it's not the best practice to give all permission to the files, if so then every user who is working on that server can access our files and manipulate the data. If you want to stay away from data leakage, hacking attacks and unnecessary errors then you have to protect your files and directories with suitable permissions.

File permissions and Access Control Lists (ACLs) are two mechanisms in Linux that control access to files and directories. They both play crucial roles in managing security and determining who can read, write, and execute files. let's understand them one by one.

### ⚒️File Permissions:🛠️

File permissions in Linux determine the level of access that the owner, group, and others have for a file or directory. The three digits/alphabets correspond to the permission levels for the owner, group, and others, respectively.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689844323730/81b3a046-e93f-48fc-a73b-5e09eb91bb0d.png align="center")

### 🗂️Manage file permission using the alphabet:🆎

It's a simple one, three alphabets is managing access to the file read(r), write(w), and execute(x). let's create one file and check its default permissions,

After creating files you have to use the ls -ltr command to check its permission.

```plaintext
user@hostip:~$ touch Devops
ser@hostip:~$ ls -ltr
```

**output:**

```plaintext
-rw-rw-r-- 1 ubuntu ubuntu        0 Jul 20 09:24  Devops
```

Look at the permission, the last three alphabet shows the permission for users(others) and it only has read permission. Let's assign write and execute permission to the user,

```plaintext
user@hostip:~$ chmod u+wx Devops
```

**output:**

```plaintext
-rw-rw-rwx 1 ubuntu ubuntu        0 Jul 20 09:24  Devops
```

Compare the permission now, we were successfully assigned the write and execute permissions to the DevOps file, for users.

### 🗂️Manage file permission using Numbers:8️⃣9️⃣

In Linux, file permissions are represented using a three-digit octal number (base-8). Each digit represents the permission for different user groups: owner, group, and others. Each digit is a sum of three binary values (4 for read, 2 for write, and 1 for execute). Here's the breakdown:

* 4: Read permission (r)
    
* 2: Write permission (w)
    
* 1: Execute permission (x)
    
* You can also use a combination of them like for **read-write 6**, **read-execute 3** etc.
    

As we saw in the last section, we assigned the write, execute permission to the Devops file for the user, now let's do that with the help of numbers,

```plaintext
user@hostip:~$ chmod 3 Devops
```

**output:**

```plaintext
--------wx 1 ubuntu ubuntu        0 Jul 20 09:24  Devops
```

> Note: Notice the permission when you used the numeric format you also have to pass permission for owners and groups otherwise its overrides all the permission. In the above case, we were only passed to others. If you want to assign permission for owners and groups use **chown**, **chgrp** respectively.

### 🎃Access Control Lists (ACLs):🎃

While file permissions cover the basic access control for the owner, group, and others, ACLs allow for more fine-grained control over access rights. ACLs allow you to set permissions for specific users and groups beyond the traditional owner and group.

With ACLs, you can grant or deny permissions to specific users or groups on a file or directory. This is particularly useful in scenarios where you need to provide custom access to multiple users without changing the underlying group ownership.

The `getfacl` and `setfacl` commands are used to view and modify ACLs, respectively. For example:

```plaintext
user@hostip:~$ getfacl Devops
output:
# file: Devops
# owner: ubuntu
# group: ubuntu
user::---
group::---
other::-wx
```

Now create one user and assign read-write permission to it,

```plaintext
user@hostip:~$ sudo useradd Rishi
user@hostip:~$ setfacl -m u:Rishi:rw- Devops
output:
# file: Devops
# owner: ubuntu
# group: ubuntu
user::---
user:Rishi:rw-
group::---
mask::rw-
other::-wx
```

### 🔅Conclusion:🔁

Above mentioned information is much important for a DevOps engineer as he has to manage servers and security. Also if a new member comes into the team, assign appropriate permission to him, and add him to a group.

So I encourage you to try this on your own and let me know in the comment section about your learning experience.

Thanks for reading, Stayed tuned for such amazing blogs.

Happy Learning...!
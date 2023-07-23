---
title: "Introduction to Ubuntu."
datePublished: Sun Jul 16 2023 10:08:08 GMT+0000 (Coordinated Universal Time)
cuid: clk59x71k00000al4bm4sbxjd
slug: introduction-to-ubuntu
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689501731683/c646eb18-7a53-42f3-b0cf-3f797c7b5e58.webp
tags: ubuntu, blogging, devops, 90daysofdevops

---

### What is Operating System(OS)?

An operating system is software that provides a suitable platform for running your applications and also allocates required resources like storage, RAM etc. to your applications to run smoothly.

There are so many OS available in the market like Windows, macOS, Unix, Linux etc. Out of them, Linux is open source.

### What is open source?

Open source is a type of software that we can use without purchasing the license, it's free to use. Also, we can modify its source code according to our requirements. Linux, centos, ubuntu, RHEL, and SUSE all are open-source OS.

### Basic commands for Ubuntu:

* To check your present working directory,
    

```plaintext
user@hostip:/$ pwd
```

* To make a new directory,
    
    ```plaintext
    user@hostip:/$ mkdir <your_directory_name>
    ```
    
* To make a directory inside the directory using one command use the Parent flag,
    
    ```plaintext
    user@hostip:/$ mkdir -p <outer_dir>/<inner_dir>
    ```
    
* To list the file in a directory,
    

```plaintext
user@hostip:/$ ls
```

To change the directory,

```plaintext
user@hostip:/$ cd <directory_name>
```

* To go back from the current directory,
    
    ```plaintext
    user@hostip:/$ cd ..
    ```
    
* To list the hidden files of the directory, (files starting with . or .. are hidden)
    

```plaintext
user@hostip:/$ ls -a
```

* To check the version of your ubuntu os,
    
    ```plaintext
    user@hostip:/$ lsb_release
    ```
    
* This is for all os,
    
    ```plaintext
    user@hostip:/ cat /etc/os-release
    ```
    
    ### Basic operations on Ubuntu,
    
* To copy the file from one directory to another,
    
    ```plaintext
    user@hostip:/$ cp <parent_dir_name>/<file_name> <destination_dir_name>
    ```
    
* To move the files to a different directory and Rename the files
    

```plaintext
user@hostip:/$ mv <parent_dir_name>/<file_name> <destination_dir_name>

user@hostip:/$ mv <old_file_name> <new_file_name>
```

* To remove the file,
    

```plaintext
user@hostip:/$ rm ,file_name>
```

* To remove the directory,
    
    ```plaintext
    user@hostip:/$ rm -r <dir_name>
    ```
    
* ### conclusion:
    
    Above mentioned commands are basic, I suggest you try this so you can get a good idea and also you will become familiar with the terminal.
    
    If you can face an issue while trying this command feel free to ask your doubt in the comment section.
    

Thanks for your time, If you find this valuable follow me on hashnode.

Stay tuned for such amazing blogs...!
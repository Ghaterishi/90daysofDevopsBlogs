---
title: "Shell Scripting for beginners"
datePublished: Tue Jul 18 2023 18:17:32 GMT+0000 (Coordinated Universal Time)
cuid: clk8ma9kv000009lef9jx80cg
slug: shell-scripting-for-beginners
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689703978828/8ff87c4a-766a-4ba4-a7f9-d6eb4e19a08a.png
tags: bash, shell-script, 90daysofdevops, day4, binbash

---

In this blog, we will learn about shell scripting. But first, you have to go through Linux architecture to understand it better.

### 📌Linux Architecture:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689696484182/9d9ccf7a-ba17-406c-8d62-e945a2bd04cb.png align="center")

Above mention diagram shows the typical architecture of Linux-based operating systems. let's understand its components one by one.

1. Applications: These are the software packages which you install on your system for doing your day-to-day tasks. like Notepad, Vscode, python etc.
    
2. Shell: A shell is a command-line interface (CLI) or text-based user interface provided by an operating system that allows users to interact with the computer and execute commands. It's like an interpreter between the application and Kernal, whatever commands you write on the terminal, the shell passes it to Kernal.
    
3. Kernal: It's the main one, it's understanding your command processing it and giving you the desired results. kernel build using C and CPP.
    
4. Hardware: you can consider this as a terminal or other peripheral device.
    

### 📌Types of shell:

* Bourne Again Shell (bash)
    
* Korn Shell (ksh)
    
* Z Shell (zsh)
    
* C Shell (csh)
    

In this blog, we are using a bash shell.

The main purpose of using shell scripting is to automate repetitive tasks.

### 🧐understanding shebang:

**#!bin/bash** is called shebang or hashbang, we mention this on the first line of the script to understand this file is the script. we can also use **#!/bin/sh,** but this is only for the Bourne shell interpreter.

The purpose of the shebang is to provide a convenient way to run scripts without explicitly specifying the interpreter each time. When a script file is executed, the operating system reads the shebang line and invokes the interpreter specified in the shebang to execute the script.

### 🥳Writing our first shell script:

First, make one file let's say Devops.sh, in this we will print a random message.

```plaintext
user@hostip:~$ touch Devops.sh
user@hostip:~$ vim devops.sh
echo"Welcome to my Blogs...!"  #add this line to your file
```

The above code snippet shows we create one file called Devops.sh and add simple command in it using Vim editor.

> Note: Every script file ends with .sh extension and to run the script we have to use bash or ./ before the file name.

```plaintext
user@hostip:~$ ./Devops.sh
output:
Welcome to my Blogs...!
```

### 📌Update your server and install docker on it using a script:

```plaintext
user@hostip:~$ vim docker.sh
sudo apt-get update -y
sudo apt-get install dockcer.io

user@hostip:~$ bash docker.sh
```

Above code snippet, we created one script called docker.sh b using vim editor and two commands in it and then run that script. if you want to check docker is installed on your system successfully use the following command,

```plaintext
user@hostip:~$ systemctl status docker
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689700776840/f3333f00-564b-4b99-b615-24aec77d0f1a.png align="center")

### 📌Shell Script to take user input, input from arguments and print the variables:

In this script, we will dynamically take input from the user and stored it in a variable and print the variable after successfully run the script,

```plaintext
#!/bin/bash

# Take input from the user
read -p "Enter your name: " name

# Print the variable
echo "User input: $name"

output:
Enter your name: Rishi # user gives this value
User input : Rishi # printing the variable value
```

> Note: you can use # to provide comments in the script.

### 📌Shell Script for checking the number is Odd or even using if else block:

```plaintext
#!/bin/bash

# Read a number from the user
read -p "Enter a number: " number

# Check if the number is odd or even
if [ "$((number % 2))" -eq 0 ]; then
    echo "The number is even"
else
    echo "The number is odd"
fi
```

> Note: In the shell script if else block ends with fi (reverse of if).

### 🔅conclusion:

In this blog, we learned what is shell scripting and how to write your first script along with some examples. I encourage you to try this on your own, if you try, you do mistakes and then you learn from that mistakes. it's the best way to gain expertise.

If you have any doubt please reach out to me using a comment section.

Thanks for reading....!
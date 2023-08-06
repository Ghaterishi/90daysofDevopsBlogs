---
title: "💥Docker: The Game Changer..!"
datePublished: Sun Aug 06 2023 03:23:48 GMT+0000 (Coordinated Universal Time)
cuid: clkyvq3vl000609mgd4ob6izt
slug: docker-the-game-changer
tags: docker, containers, docker-images, 90daysofdevops, trainwithshubham

---

### 📌Introduction:

Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime. Using Docker, you can quickly deploy and scale applications into any environment and know your code will run.

### 📌Why do we need docker?

* 👉Compatibility/Dependency
    
* 👉Long Setup time
    
* 👉Different Dev/Test/Prod environments.
    

### 📌What can it do?

* 👉Containerize Applications
    
* 👉Run each service with its dependencies in separate containers
    

### 📌Docker Architecture:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691257057066/84d750d9-d3ee-41c7-9faf-04f94388eece.webp align="center")

**⚒️Docker Daemon (dockerd):**

The Docker daemon (dockerd) is the core background service that runs on the host machine. It is responsible for managing containers, images, volumes, and networks. The daemon handles all the requests from the Docker client, manages the container's lifecycle, and ensures the isolation and resource allocation of containers.

**⚒️Docker Client:**

The Docker client is the command-line tool or API that allows users to interact with the Docker daemon. It sends commands to the Docker daemon, which, in turn, executes them. The client can run on the same machine as the daemon or connect to a remote Docker daemon running on another host.

### 🔁Workflow :

**Code--&gt; Dockerfile--&gt; Image--&gt; Container**

✅A **Dockerfile** is a plain-text configuration file used to define the instructions for building a Docker image. It contains a set of commands and parameters that describe how to assemble the image and configure the application environment within the container.

**✅Docker images** are read-only templates used to create containers. They contain the application code, runtime, libraries, environment variables, and other necessary files to run an application. Images are the building blocks for containers and can be stored in a local or remote registry, such as Docker Hub.

✅A **Docker container** is a runnable instance created from a Docker image. It represents a lightweight, standalone, and executable software package that includes everything needed to run an application, including code, runtime, system tools, libraries, and settings. Containers run in isolation from the host system and other containers, making them portable and consistent across different environments.

### 📌Basic Docker Commands:

* **Image related.**
    

```plaintext
docker build -t <image_tag> .  #create image
docker images                  #list images
docker rmi <image_name>        #remove image
docker pull <image_name>       #download image from docker hub
```

* **Container related**
    

```plaintext
docker run <image_name>      #run container
docker ps                    #list running container
docker ps -a                 #list all container
docker stop <cont_name>      #stop running cont
docker rm <cont_name>        #remove cont
docker run -d <cont_name>    #run cont in detach mode
```

### 📌90daysofDevopsTask

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691259101951/1e5a4235-3343-4ec4-88ec-15de719b39e9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691259121822/6e1b22f7-5e26-4619-a6f3-e0f0e7c9461f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691259133766/b843dbf0-1f78-4374-8302-db704b0bb918.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691259142129/07ffc78c-a6e5-4b90-85ae-a43711cc11db.png align="center")

### 🪧Conclusion:

Overall, Docker allows developers to build, ship, and run applications using containers, providing an efficient and consistent way to manage applications and their dependencies across different environments.

🙏Thanks for reading..!

🤝Follow me on Hashnode for such amazing content.

📌Linkedin: [**linkedin.com/in/rushikesh-ghate-525060199**](http://linkedin.com/in/rushikesh-ghate-525060199)

📌GitHub: [**github.com/Ghaterishi**](http://github.com/Ghaterishi)
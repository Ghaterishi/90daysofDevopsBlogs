---
title: "🚨Docker Advanced: Comprehensive Guide for Beginner's.🚨"
datePublished: Fri Aug 11 2023 10:02:59 GMT+0000 (Coordinated Universal Time)
cuid: cll6f6p9n000t09la9djpdfmj
slug: docker-advanced-comprehensive-guide-for-beginners
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691746208659/680caab6-0a86-4ed8-bf03-e4317ce2fa54.png
tags: docker, devops, docker-compose, docker-volume, trainwithshubham

---

### 🪧Introduction:

In the last we discussed what is docker, why we use it and its architecture. Also, we discussed some basic commands for managing docker images and containers. In this blog, we will discuss some advanced concepts like Docker volume, Docker-compose, Docker network and how to containerise apps using Docker files.

### 💥How to Containerize your app?

For containerizing app, you have to write a docker file and create an image from it. Dockefile is a list of commands required to run your application inside the containers.

> **<mark>Instructions</mark>: Arguments**
> 
> <mark>FROM </mark> ubuntu --&gt; Base image
> 
> <mark>RUN </mark> apt-get update \\ apt-get install python
> 
> <mark>RUN </mark> pip install flask \\ pip install mysql ---&gt; install dependencies
> 
> <mark>COPY </mark> . . --&gt; Copy your repo inside the container
> 
> and many more...
> 
> Note: For every application, some different libraries and dependencies need to be installed, so the Dockrefile file may vary.

When your Dockerfile is ready you just have to run the following command to create the image,

```plaintext
docker build -t <your_image_name> . --> #-t is for taging your image
```

Now your image is ready run the container using this image,

```plaintext
docker run -d -p <host_port>:<container_port> --name <cont_name> <image_name>
```

### ⚒️Contaierzing node app:

* If you already have your code just make the Dockerfile and follow the below steps or else you can fork the simple node-todo app,
    
* [Github Nodeapp Repo](https://github.com/Ghaterishi/node-todo-cicd.git)
    
* After fork make sure you have docker installed on your machine let's start building the image,
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691490657740/d151c872-2cac-472b-b5ba-d1c0efc99e2a.png align="center")
    
    After building the image run the container and check whether your app is working or not,
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691490708026/2d8b05c0-f77a-4f02-8a19-813f6813f1db.png align="center")
    
* Ping the localhost, don't forget to specify the port,
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691490830345/824073d3-d0d9-451d-9686-044179c8290a.png align="center")
    

### 🗄️Docker Storage:

Consider you have a critical containerized application which stores and fetches data, unfortunately, if that container gets crashed or delete then you will lose crucial data, that is how Docker volumes come into the picture. Docker volumes are persistent storage which gives you the capability to persist your data and stored it outside the container, so need to worry about what if the container goes down.

let's understand docker volumes and its features,

**📌Sharing Data:**

Multiple containers can use the same volume to share and exchange information. It's like having a common space/folder where multiple containers can read or write their data.

**📌Performance:**

Volumes are designed to handle data efficiently, making reading and writing data faster. It's similar to having a dedicated desk for writing or reading that's optimized for your tasks.

**📌Isolation:**

The data in the volume is separate from the container, making it easier to manage and back up.

### ⚒️Containerizing Django-app and mount volume in it:🗄️

* If you already have your code just make the Dockerfile and follow the below steps or else you can fork the simple Django-todo app using the following link,
    
* [Django-todo-app](https://github.com/LondheShubham153/django-todo-cicd.git).
    
* After fork make sure you have docker installed on your machine let's start building the image,
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691658894963/b2d2078d-4f5c-4c3c-ad5a-1441c4465ca0.png align="center")
    
* Now let's create a docker volume, after creating the volume you have to mount it on the container otherwise container data won't persist,
    
* First, create one folder for storing container data and then create volume from it,
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691659621862/3a9e6b27-030e-4b8a-bbb6-9b47ee5e5721.png align="center")
    
    **The command for creating volume:**
    

```plaintext
docker volume create --name django-volume --opt type=none --opt device=/home/ubuntu/django-volume --opt o=bind
```

* Now run the container from the pre-build image we created in step01 and mount volume on it,
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691660599363/39037231-93ca-49fa-9d77-e133b4875a46.png align="center")
    

**The command for run container with volume:**

```plaintext
docker run -d --mount source=django-volume,target=/data -p 81:8000 task2
```

* After this go to your volume directory and check you will see the file inside the containers are back up there,
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691660931098/04641539-e32e-4870-8705-1e8d3893ea93.png align="center")
    
* To check how this volume works create one sample text file inside your volume directory and check if it will be visible or not inside your container, do one more thing add something in this file from inside the container and check that content is reflected or not in your volume directory,
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691661190608/ba9300e6-ddbc-473d-871a-7ca2e2575a90.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691661216069/fe39cc75-03a1-4a18-a77f-244907669e9a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691661235663/0e5c15a2-b4fc-46b6-9696-15d2b6f3d08a.png align="center")

And Boooooom... you got it.! That's how easy Docker volume is.

### 🎁Docker Compose:

Now you got a basic idea of how to run containers, you need to run two commands docker build and docker run. This is ok for small numbers of containers but if you are working in production environments, there are so many containers running, it takes a lot of time to start and stop each container separately. So here we use Docker-compose.

* Docker Compose is a tool that was developed to help define and share multi-container applications.
    
* With Compose, we can create a YAML file to define the services and with a single command, can spin everything up or tear it all down.
    

### 🚦🚥Deploy Two-Tier-Flask-app using Docker-compose:

let's understand the basic workflow of Docker-compose and how it works, I am attaching the steps below, follow along with me,

* Clone the repository using the following link,
    
    [Two-tier-flask-app](https://github.com/LondheShubham153/two-tier-flask-app.git)
    
* Go to your app directory when the docker-compose.yml file is kept and edit the environment variables mentioned in both services.
    
* After looking docker-compose file you get a good idea that we are using two images, from which one is building(backend) and one is directly pulling from the docker hub(mysql).
    
* one more thing you need to install docker-compose separately as it is not installed with docker.io. let's discuss the command related to docker-compose,
    

```plaintext
sudo apt-get installed docker-compose #installing docker-compose
docker-compose up                     #run everything inside the compose file
docker-compose down                   #stop everything inside the compose file
```

* now run the **docker-compose -d** command inside your app directory and ping the localhost:5000 from your browser, what you see is an Error. Oh..no don't bother we will resolve this soon.
    

> Make sure you open port 5000 in your server inbound rule if you're using a cloud VM.

* Go inside your mysql container and open mysql client. create a database the name should be the same as you mentioned in compose file and create one table called messages.
    
    ```plaintext
    docker exec -it <cont_id> bash   # to go inside container
    mysql -u <your_username> -p      #press enter 
    use <your_database_name>;  #to go inside your database
    create table messages (message varchar(255)); #to create table
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691737606103/c5afc280-22dd-42a1-955b-2939af18ba16.png align="center")
    
* Now refresh your browser screen and boom, you got it.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691737983739/f02d7dfc-3620-4e7d-8723-962166333e33.png align="center")
    
* Now run the **docker-compose down** command you will see both containers stop within seconds, again start the container using the **up** command, now you don't need to create a database and table because we already attached a volume to our container.
    
* we noticed that one container of each service is getting deployed, if you want to increase the container of a specific service use d**ocker-compose --scale backend=3.**
    
* That's all for Docker-compose. Now you are a master of it.
    

### 🌐Docker Network:

Docker networking is like creating a virtual road system that connects all your containers. This road system allows your containers to send messages, share data, and collaborate.

When you set up Docker networking, you're giving each container its address on the virtual road. This address lets containers find and talk to each other easily. So, if one container has some important information, it can share it with other containers on the same network.

### 💻Types of Network:

when you install docker it automatically creates one separate network for containers which is the docker network. Below are the types of Docker networks,

**📌Bridge Network**:

This is the default network type that Docker sets up for you. Containers on the same bridge network can communicate with each other directly using their names, and Docker handles IP address assignments. This is like a private network for your containers.

> example: Run a container using nginx but don't expose the port and check you can access that container from a web browser, unfortunately you don't, because you don't expose the port. Docker already creates a bridge network between your host and docker container, you need to use that bridge.
> 
> ```plaintext
> docker run -d nginx          #cant access from browser
> docker run -d -p 80:80 nginx #accessable (use bridge net)
> ```

**📌Host Network**:

When you connect a container to the host network, it shares the host's networking namespace. This means the container uses the host's network directly without any isolation. It's useful when you need to have the container share the same network as the host.

> example: Now follow the steps above and run the following command, when you're using the host network you don't need to expose ports.
> 
> ```plaintext
> docker run -d --name nginx --network host nginx
> ```

**📌Overlay Network:**

Overlay networks are used in Docker Swarm, which is Docker's native orchestration tool for managing large groups of containers. Overlay networks allow containers to communicate with each other across multiple Docker hosts (machines) in a Swarm cluster. This is useful for creating services that need to scale and be highly available across different machines.

**📌Macvlan Network:**

This type of network allows containers to have MAC addresses that are part of the physical network, making them appear like separate physical machines. It's useful when you need containers to be directly reachable on the same network segment as physical devices.

**📌None Network:**

Containers on a "none" network have no external connectivity. They can only communicate with other containers on the same network.

### 🌀Conclusion:

As you see, we discussed most of the docker concepts and also deploy three different apps like node, Django, and flask. I encourage you all the follow this blog and try to do it on your own as it gives you a good understanding. You can also add these projects to your resume to showcase your expertise in docker.

🙏Thanks for reading..!

🤝Follow me on Hashnode for such amazing content.

📌Linkedin: [**linkedin.com/in/rushikesh-ghate-525060199**](http://linkedin.com/in/rushikesh-ghate-525060199)

📌GitHub: [**github.com/Ghaterishi**](http://github.com/Ghaterishi)
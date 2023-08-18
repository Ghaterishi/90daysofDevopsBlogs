---
title: "🚀Jenkins: Basic to Advanced . P-1🚀"
datePublished: Fri Aug 18 2023 17:41:36 GMT+0000 (Coordinated Universal Time)
cuid: cllgvngs2000a0alcdx7h7ior
slug: jenkins-basic-to-advanced-p-1
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692367185791/7cbbe0b4-c77d-471d-a35c-66d71d144ec3.png
tags: devops, jenkins, ci-cd, 90daysofdevops, trainwithshubham

---

### 🪧Introduction:

In today's world, every field needs automation as it reduces human errors. Humans are more likely to cause an error compared to a machine, also to do a specific task manually requires more time and attention, so why not establish a mechanism to automate the processes?

In this blog, we will discuss how to integrate and deploy your software application faster using Continuous integration and continuous deployment process. This is part of automation only which we called CI/CD. The best and most popular tool for building pipelines is Jenkins.

Let's understand more about Jenkins.

### 🚦What is CI/CD?

CI stands for "Continuous Integration." It is a software development practice that involves regularly integrating code changes from multiple contributors into a shared repository. The main goal of CI is to detect and address integration issues, bugs and conflicts early in the development process, rather than waiting until the end. This helps to improve the quality of software and streamline the development workflow.

CD stands for "Continuous Deployment". In Continuous Deployment, once the code changes have gone through the CI process and passed all automated tests, they are automatically and immediately deployed to the specific environment(dev/test/prod). This means that whenever developers make changes and those changes are approved through testing, they are automatically released to the live version of the software without manual intervention.

### 🚦What is Jenkins?

Jenkins is an open-source automation software that helps automate various parts of the software development process. it's written in Java, so you need to install Java first to run Jenkins on your machine. It's a popular tool used for Continuous Integration and Continuous Deployment (CI/CD) to streamline the building, testing, and deployment of software.

### 🚦Jenkins Components and Terminology:

**📌Job:** A job is a task that you want Jenkins to perform. It could be building a specific project, running tests, deploying software, etc.

**📌Build:** A build is a process of transforming source code into a deployable software artifact. This can involve compiling code, running tests, and creating executable files.

**📌Pipeline:** A pipeline is a series of steps that define the process of building, testing, and deploying software. Jenkins pipelines can be written using code, often using a tool called "Jenkinsfile."

**📌Jenkinsfile:** A Jenkinsfile is a text file that contains the definition of a pipeline using a domain-specific language. It's like a script that tells Jenkins what to do at each step of the pipeline.

**📌Stage:** A stage in a pipeline is a distinct part of the process, like "Build," "Test," or "Deploy." Pipelines are divided into stages to organize the workflow and make it easier to understand.

**📌Node/Agent:** A node (also called an agent) is a machine that Jenkins uses to execute tasks. It can be a physical server, a virtual machine, or even a container.

**📌Master:** The Jenkins master is the main control hub. It's the part of Jenkins that manages all the nodes, schedules jobs, and coordinates the overall workflow.

**📌Trigger:** A trigger is an event that starts a Jenkins job. It could be a code commit, a scheduled time, or some other condition.

**📌Plugin:** Jenkins is highly extensible through plugins. Plugins add extra functionalities to Jenkins, allowing you to integrate it with various tools, services, and technologies.

**📌SCM (Source Code Management):** SCM refers to tools like Git, SVN, and others that help manage and version control the source code of a project.

**📌Freestyle Project:** A Freestyle Project in Jenkins is a type of project configuration that allows you to define a series of build steps and actions using a UI. It's a traditional approach where you can specify individual build steps, such as code checkout, compiling, testing, and deployment, by configuring them through the Jenkins UI. Each step is executed sequentially, and you have flexibility in defining the order and configuration of these steps. It's akin to composing a custom workflow by selecting and arranging building blocks tailored to the project's requirements.

**📌Pipeline:** A Pipeline in Jenkins, often referred to as "Jenkins Pipeline," is a suite of plugins that provides a way to define software delivery workflows as code. It offers a powerful and programmable approach to defining the entire software lifecycle as a series of stages and steps. Pipelines are typically defined using a domain-specific language, such as the Groovy-based "Jenkinsfile." This provides a structured and maintainable way to automate end-to-end software delivery processes with repeatability and transparency.

### 🚦Installation of Jenkins on Linux:

[Jenkins Docs](https://www.jenkins.io/doc/book/installing/linux/)

### 🚦Set up your first Jenkins freestyle Job for the Node app:

* First Paste your server ip with the 8080 port as Jenkins runs on this port, then create an admin user to use Jenkins smoothly and set up jobs and pipelines using the Jenkins dashboard.
    
* After the above step click on New Item or New Job option on the dashboard and filled the nessecry details like project description, GitHub URL and build step. Leave build triggers as empty as it is a freestyle project.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692363285509/ccadff6b-3ee2-496f-9653-f6ca5add19b3.png align="center")
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692363310408/754c73c5-d679-4d54-b3fc-75545e8a2c0c.png align="center")
    

> Note: If you do not have code fork this repo from the below url.
> 
> [Nodo-todo-app](https://github.com/Ghaterishi/node-todo-cicd)

* After configuring all the details click on the build now option mentioned right side panel of the dashboard, and start checking the console output for any upcoming errors.
    

> Note: you will face two common errors first docker is not found for this you have to install docker on your Jenkins server and second is permission denied for this you have to add Jenkins user in the Docker group.

This how the Console output looks like,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692363949918/5ea59299-2b82-45e9-a1a8-7505814df446.png align="center")

* After successful delivery, your app is working correctly check using the public IP of your server and the specific port on which your app is running and one more point don't forget to open that port on the SG of your server and Booooom...!
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692364144072/89c3c71d-dfd2-40e5-a740-0f0171498356.png align="center")
    
    ### 🚦How to create Jenkins Agent:
    
    If you want to deploy your app on a different server, not on the master on which you installed Jenkins then the Jenkins agent comes into the picture.
    
* Creation of an agent is a bit confusing, you have to click on add node and fill in the details like description, label, home directory etc. and select launch method as Launch agent via ssh, fill in your host-IP and credentials.
    
* For credentials, you have to create them first, for that then run the **ssh-keygen** command on your master Jenkins server and copy the generated private key.
    
* Go to Jenkins dashboard and click on manage Jenkins then credentials and fill the all the details, fill in the username same as slave server and ssh key paste your private key and save.
    
* After this copy your Public and paste it into an authorized folder in .ssh directory on your slave server.
    
* Understand the scenario now your Jenkins (master) agent has a private key stored as credentials with a slave username and the public is stored on Jenkins slave so now they are ready to connect.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692366791102/c7b8ec1d-a6a7-4535-9950-f4e5048860d4.png align="center")
    
    For a better understanding watch this video, how to set up above mentioned steps,
    
    📌[setup Jenkins agent for the master-slave architecture](https://youtu.be/Se7JtzFVZGE)
    

### 🌀Conclusion:🌀

In this blog, we discussed most of the Jenkins concepts with the project. I highly encourage you to go and try it on your own. In the next blog, we will discuss how to use Jenkins in production(master & slave strategy) and how to integrate GitHub using GitHub webhook.

Stayed tuned for the next blog.!

🙏Thanks for reading..!

🤝Follow me on Hashnode for such amazing content.

📌Linkedin: [**linkedin.com/in/rushikesh-ghate-525060199**](http://linkedin.com/in/rushikesh-ghate-525060199)

📌GitHub: [**github.com/Ghaterishi**](http://github.com/Ghaterishi)
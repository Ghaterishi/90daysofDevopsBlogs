---
title: "🚀Jenkins: Basic to Advanced. P-2🚀"
datePublished: Sun Aug 20 2023 03:48:29 GMT+0000 (Coordinated Universal Time)
cuid: clliwrrln000609l212s3czud
slug: jenkins-basic-to-advanced-p-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692464693614/ea3ba28d-d499-4f27-9b4a-840467a2f6ca.png
tags: devops, jenkins, pipeline, ci-cd, 90daysofdevops

---

### Introduction:

In the last Blog, we discussed Jenkins and its component, Like what is freestyle project, how to set up it and the main one how to add an agent. I suggest you before reading this blog go and read part-1 so you understand this blog better. in this blog, we will discuss how to deploy applications on Jenkins Slave using the Jenkins master server.

### ✅What is GitHub webhook?

A GitHub webhook is a feature provided by GitHub that allows you to receive automated notifications and events from a GitHub repository to an external web server or application. These notifications are sent in the form of HTTP POST requests to a URL that you specify, commonly known as a webhook URL. Webhooks are commonly used for various purposes, such as triggering actions or integrations based on events that occur within a repository.

### ✅How to Integrate it with Jenkins?

* 📌Go to your GitHub repository and click on setting, you can see the webhook option mentioned on the left side,
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692460526610/6835b657-15a7-4c96-b4a0-9d825570a64a.png align="center")
    
* 📌After this click on add webhook and fill your Jenkins master IP address in the payload URL append with GitHub-webhook,
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692460644541/a2c7e4e0-f28b-4450-900d-1695658ccecc.png align="center")
    
* 📌Now your Github repo and Jenkins master server are connected, in future, if any push event happened in your repo git will notify Jenkins.
    

### ✅Deploy two-tier flask app on Jenkins slave server:

* 📌hope you already set up a Jenkins agent using my last blog we will use this for deploying an app on the slave server.
    
* 📌Now create one EC2 instance named Jenkins slave and copy the public key which you generated on the master server and paste it under.ssh/ authorized keys on the slave server. if you faced any trouble doing this please go through my last blog.
    
* 📌Now try to connect the slave server to the master server using the ssh command,
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692461320144/17060585-fd4b-4688-850e-1ef5d02379b4.png align="center")
    
* 📌Now you are ready to create a pipeline, let's get started.
    
* 📌Go to Jenkins dashboard and create a new job select type as pipeline,
    
* 📌mention all the details like description, repo URL, and choose build trigger as GitHub hook trigger
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692462450017/d44e9314-3cd4-4ef1-b833-675e456e6b61.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692462512272/199e5912-c4e4-434d-acb5-766e31e56069.png align="center")

* 📌You can see the above scripts mention stages for the clone, build and deploy, it's a groovy syntax, we declare stages via this that's why it's called a declarative pipeline.
    
* 📌Now do some changes in your repo and commit it, your pipeline will automatically trigger if you did all the steps correctly,
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692464222917/e8fe3c2a-c0d7-450f-a1ea-96b4b10293e6.png align="center")
    
* 📌Now copy the server IP and paste it on the browser and boom...!
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692464316557/5dbcf3db-70ab-4752-956c-80767cf3476c.png align="center")
    

### 🌀Conclusion:🌀

In this blog, we discussed how to create a declarative pipeline, the same one used in production env in companies. I highly encourage you to go and try it on your own for better understanding..!

Stayed tuned for the next blog.!

🙏Thanks for reading..!

🤝Follow me on Hashnode for such amazing content.

📌Linkedin: [**linkedin.com/in/rushikesh-ghate-525060199**](http://linkedin.com/in/rushikesh-ghate-525060199)

📌GitHub: [**github.com/Ghaterishi**](http://github.com/Ghaterishi)
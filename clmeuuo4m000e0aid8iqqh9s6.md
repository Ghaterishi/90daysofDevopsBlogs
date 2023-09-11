---
title: "🚀Introduction to kubernetes 🚀"
datePublished: Mon Sep 11 2023 12:23:23 GMT+0000 (Coordinated Universal Time)
cuid: clmeuuo4m000e0aid8iqqh9s6
slug: introduction-to-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694434881057/93e39dfc-6d68-48d0-a022-69605382595c.webp
tags: kubernetes, troubleshooting, 90daysofdevops, trainwithshubham, k8sarchitecture

---

### 🪧Introduction:

You might have heard this word before, k8s. Often, people call Kubernetes as k8s because in between k and s, there are 8 letters. As you already know what containers are, how they are built and how they make our life easy. Now let's dive into container orchestration, K8s is a container orchestration tool.

In this blog, we will discuss the basic concepts of K8s, its architecture and more. This blog gives you a good overview of the most popular orchestration tool K8s. Let's get started..!

### 📌What is container orchestration?

Container orchestration is the art of automating the deployment, scaling, management, and networking of containerized applications.

Let's consider you have lots of containers each containing a specific part/service of the application, as your app grows there will be more containers. Containers are quite simple you can run them wherever you want its do their work, but what if anyone goes down which contains an imp service of your application or there is so much load on the container that it crashes, not able to fulfil all the request, here container orchestration comes into the picture. As we move forward you will understand it better.

### ⚒️Kubernetes Architecture:⚒️

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692791858658/99911eab-cd21-4e27-91d0-65dedd3cab65.webp align="center")

In the above image, you can see there are 6 components, 4 in the control plane and 2 in the worker. There is one more component called kubectl which is a command line utility for users to interact with the k8s cluster.

Now let us understand each component one by one,

**📌ETCD**: ETCD is a distributed reliable key-value store that stores the state of k8s objects like pod running or stopped, which pod is scheduled on which node and many more. It's simple, secure and fast.

**📌Kube API-Server:** It's an entry point of the cluster, Your kubectl command directly talks to the API server and its process further, like authenticating users, validating requests, retrieving data, updating etcd, schedular and kubelet.

**📌Kube Controller Manager:** The controller manager is responsible for maintaining the desired state of the cluster. Various controllers (e.g., ReplicaSet, Deployment) continuously monitor the state of resources and make adjustments to ensure they match the desired state.

**📌Kube schedular:** You can understand by its name, that its task is to schedule the pods in available nodes, according to resource requirements, limits, taint and tolerations, and node selector.

**📌Kubelet**: Kubelet is the agent running on each worker node. It communicates with the API server and ensures that containers are running in a Pod as specified in the Pod manifest.

**📌Kube Proxy**: Kube Proxy maintains network rules on the worker nodes. It helps to manage network communication to and from pods within the cluster.

**📌Manifest files:** These are configuration files that describe the desired state of Kubernetes resources within a cluster. These resources can include pods, services, deployments, replica sets, config maps, and more. Manifest files are typically written in YAML or JSON format and are used to define how Kubernetes should create, configure, and manage these resources.

### 🚦K8s objects:🚦

1. **Pod**: A pod is the smallest and simplest object in Kubernetes. It's like a single instance of a containerized application. Pods can contain one or more containers that share the same network and storage. Pods are where your actual application code runs.
    
2. **Service**: A service is an object that defines a set of pods and provides a stable network endpoint to access them. It ensures that your application remains accessible even as pods come and go. Think of it as a load balancer for your pods.
    
3. **Deployment**: A deployment is an object that manages the desired number of replica pods for your application. It allows you to easily scale your application up or down, roll out updates, and roll back to previous versions.
    
4. **Namespace**: A namespace is like a virtual cluster inside a Kubernetes cluster. It's used to group and isolate resources, allowing you to manage multiple projects or teams within a single cluster.
    
5. **ConfigMap and Secret**: These objects store configuration data and secrets separately from your application code. They help keep your configuration separate from your containers, making it easier to manage and update.
    
6. **Volume**: Volumes are used to provide persistent storage to your pods. They allow data to survive pod restarts or rescheduling to different nodes.
    
7. **Ingress**: An ingress is an object that manages external access to services within your cluster. It allows you to define routing rules for different services based on URLs and paths.
    

### ✅Installation of K8s:

You can use the below repo to install both ways,

**👉MInikube**: For learning purposes.

**👉Kubeadm**: To learn how companies use K8s in production.

[GitHub repo](https://github.com/Ghaterishi/kubestarter).

### 📝Creating K8s Objects:

First, create a Namespace called nginx to group all the resources related to it,

```plaintext
Kubectl create namespace nginx
```

Now let's create a pod inside that namespace, write a manifest file for the pod (nginx.yml)

```plaintext
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
  namespace: nginx  # Specify the desired namespace here
  labels:
   app: my-app
spec:
  containers:
  - name: my-first-pod
    image: nginx:latest
```

Now create a pod and check your pod is running,

```plaintext
Kubectl apply -f nginx.yml 
kubectl get pods -n nginx
```

Now access this pod from the web. First, you have to create a service, write a service manifest file,

```plaintext
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
  namespace: nginx
spec:
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: NodePort
```

Create a service like a pod, using the kubectl command,

```plaintext
kubectl apply -f service.yml
kubectl get svc -n nginx
```

Check the SVC port which port mapped to 80 and use node public IP with nodeport and boom..!

Note: Open the node port in SG of your worker node.

### 📚Deploying Two-Tier Flask app:

**🧲Step-01: Clone the below repo on your machine,**

🔗[Github repo](https://github.com/Ghaterishi/two-tier-flask-app.git)

**🧲Step-02**: After cloning the code, check the content inside the k8s directory I placed all the manifest files there.

**⚙️Overview**:

There are two deployments one for the backend which is the Flask todo app and one for MySQL which stores todo tasks.

Also, two services are there, to expose the backend pod on the internet we used nodeport service and for connecting the database internally to the backend pod we used clusterip service.

For storing environment variables of MySQL pod we create Configmap and for storing sensitive information like passwords we create secret manifes. After this, we give this variable reference in our backend pod to use this variable.

**🧲Step-03: Apply all manifest files one by one,**

```plaintext
kubectl apply -f mysql-configmap.yml
kubectl apply -f mysql-secret.yml
kubectl apply -f mysql.yml
kubectl apply -f mysql-svc.yml
kubectl apply -f backend.yml
kubectl apply -f backend-svc.yml
```

**🧲Step-04: Open nodeport in SG of the worker node,**

First, check the nodeport expose on the internet by using **Kubectl get svc** command, and then open that port in the security group.

**🧲Step-05: Access the app from the browser,**

Copy your worker node public ip and paste it into the browser with nodeport and Booom.....!

Congratulations on your first app deployment using Kubernetes.

**⏳Step-05: Troubleshooting,**

1. If your backend pod not getting connected to the database pod and facing a similar issue as mentioned below,
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694433636265/d4ee3e76-f895-4539-b1ae-3394e44c254d.png align="center")

Run the command **kubectl get svc**, copy the clusterip of MySQL service and paste it in the backend pod deployment file under the env MYSQL\_HOST(its value).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694434798912/b0bdfab9-7c2f-4944-aa64-329f144cf837.png align="center")

1. If you get a table not found the issue then go to the worker enter into the MySQL container and create one table,
    
    ```plaintext
    docker exec -it <mysql_pod_name> /bin/sh
    mysql -u <user> -h <mysql_service_name> -p 
    #after this you enter into the mysql cmd then create table
    Mysql> use mydb;
    mysql> create table messages (message varchaar(255));
    ```
    

### 🎊Conclusion:

After reading and following the instructions mentioned in this blog, you will get a basic understanding of og k8s, how it works and the main one which is the manifest files. I highly encourage you to try this on your own to understand better.

🙏Thanks for reading..!

🤝Follow me on Hashnode for such amazing content.

📌Linkedin: [**linkedin.com/in/rushikesh-ghate-525060199**](http://linkedin.com/in/rushikesh-ghate-525060199)

📌GitHub: [**github.com/Ghaterishi**](http://github.com/Ghaterishi)
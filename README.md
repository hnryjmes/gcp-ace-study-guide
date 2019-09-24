# Official Google Cloud Platform Associate Cloud Engineer Study Guide

### by Dan Sullivan

`Notes by Henry Cooksley`

### Introduction

"Deploying and managing applications and services in GCP requires a clear understanding of the way Google structures user accounts and manages identities and access controls; you also need to understand the advantages and disadvantages of using various services."

Chapter 1: Overview of Google Cloud Platform

Chapter 2: Google Cloud Computing Services

Chapter 3: Projects, Service Accounts, and Billing

Chapter 4: Introduction to Computing in Google Cloud

Chapter 5: Computing with Compute Engine Virtual Machines

Chapter 6: Managing Virtual Machines

Chapter 7: Computing with Kubernetes

Chapter 8: Managing Kubernetes Clusters

Chapter 9: Computing with App Engine

Chapter 10: Computing with Cloud Functions

Chapter 11: Planning Storage in the Cloud

Chapter 12: Deploying Storage in Google Cloud Platform

Chapter 13: Loading Data into Storage

Chapter 14: Networking in the Cloud: Virtual Private Clouds and Virtual Private Networks

Chapter 15: Networking in the Cloud: DNS, Load Balancing, and IP Addressing

Chapter 16: Deploying Applications with Cloud Launcher and Deployment Manager

Chapter 17: Configuring Access and Security

Chapter 18: Monitoring, Logging,and Cost Estimating

### 1 Overview of Google Cloud Platform

Types of Cloud Services

Compute Resources

Virtual Machines

"Google Cloud Platform offers a variety of preconfigured VMs with varying numbers of vCPUs and amounts of memory."

"You can also create a custom configuration if the preconfigured offerings don't meet your needs."

"You have full access to the VM, so you can configure file systems, add persistent storage, patch the operating system, or install additional packages."

"A VM that you manage is like having a server in your office that you have full administrator rights to."

"If one of the VMs in a cluster fails, the workload can be directed to the other VMs in the cluster."

"Autoscalers can add or remove VMs from the cluster based on the workload."

Managed Kubernetes Clusters

"A container is like a lightweight VM that isolates processes running in one container from processes running in another container on the same server."

"Containers are good options when you need to run applications that depend on multiple micro services running in your environment."

Serverless Computing

"Google Cloud Platform has two serverless computing options: App Engine and Cloud Functions."

"App Engine is used for applications and containers that run for extended periods of time, such as a website backend, point-of-sale system, or custom business application."

"Cloud Functions is a platform for running code in response to an event, such as uploading a file or adding a message to a message queue."

Storage

Object Storage

"Object storage is a system that manages the use of storage in terms of objects or blobs."

"Usually these objects are files,but it is important to note that the files are not stored in a conventional file system."

File Storage

"File storage is suitable for applications that require operating system-like file access to files."

Block Storage

"Block storage uses a fixed-size data structure called a block to organize data."

"In Linux file systems, 4KB is a common block size."

Caches

"Caches are in-memory data stores that maintain fast access to data."

"The latency of in-memory stores is designed to be submillisecond."

"If you decide to use a cache, be sure to design a cache update strategy that meets your requirements for consistency between the cache and the system of truth."

Networking

"Each network-accessible device or service in your environment will need an IP address."

"In fact, devices within GCP can have both internal and external addresses."

"Your internal GCP network is defined as a virtual private cloud (VPC)."

"External IP addresses can either be static or ephemeral."

"Static addresses are assigned to a device for extended periods of time."

"Ephemeral external IP addresses are attached to VMs and released when the VM is stopped."

"In addition to specifying IP addresses, you will often need to define firewall rules to control access to subnetworks and VMs in your VPC."

"You may need to share data and network access between an on-premise data center and your VPC."

"You can do this using one of several types of peering, which is the general term for linking distinct networks."

Specialized Services

Cloud Computing vs. Data Center Computing

Rent Instead of Own Resources

"The unit cost of running servers in the cloud may be higher than that of running the equivalent server in the data center, but the total cost of on-premise and short-term in the cloud mix of servers may still be significantly less than the cost of purchasing or leasing for peak capacity and leaving resources idle."

Pay-as-You-Go-for-What-You-Use Model

Elastic Resource Allocation

"Extensive resources and the ability to quickly shift resources between customers enables public cloud providers to offer elastic resource allocation more efficiently than can be done in smaller data centers."

Specialized Services

Exam Essentials

"Understand different ways of delivering cloud computing resources."

"Understand the different forms of cloud storage and when to use them."

"Understand the differences between running an IT environment on-premise or in the cloud."

Review Questions

1. What is the fundamental unit of computing in cloud computing? - B. VM

- B. The basic unit for purchasing computing resources is the virtual machine (VM). A physical server underlies VMs, but the resources of a physical server are allocated to VMs. Blocks and subnets are not relevant to the fundamental unit of computing.

2. If you use a cluster that is managed by a cloud provider, which of these will be managed for you by the cloud provider? - D. All of the above

- D. When using managed clusters, the cloud provider will monitor the health of nodes in the cluster, set up networking between nodes in the cluster, and configure firewall and other security controls.

3. You need serverless computing for file processing and running the backend of a website; which two products can you choose from Google Cloud Platform? - B. App Engine and Cloud Functions

- B. App Engine is a serverless platform for running applications, while Cloud Functions is a service for executing short-running functions in response to events. Kubernetes Engine is a managed cluster service, and both Kubernetes Engine and Compute Engine require you to configure servers.

4. You have been asked to design a storage system for a web application that allows users to upload large data files to be analyzed by a business intelligence workflow. The files should be stored in a high-availability storage system. File system functionality is not required. Which storage system in Google Cloud Platform should be used? - B. Object storage

- B. Object storage, like Cloud Storage, provides redundantly stored objects without limits on the amount of data you can store, which makes option B correct. Since file system functionality is not required, option D is not a good option. Block storage could be used, but you would have to manage your own replication to ensure high availability. Caches are transient, in-memory storage and are not high-availability, persistent storage systems.

5. All block storage systems use what block size? - D. Block size can vary.

- D. Block sizes in a block storage system can vary; therefore, option D is the correct answer. Block size is established when a file system is created. 4KB block sizes are commonly used in Linux.

6. You have been asked to set up network security in a virtual private cloud. Your company wants to have multiple subnetworks and limit traffic between the subnetworks. Which network security control would you use to control the flow of traffic between subnets? - C. Firewall

- C. Firewalls in Google Cloud Platform (GCP) are software-defined network controls that limit the flow of traffic into and out of a network or subnetwork, so option C is the correct answer. Routers are used to move traffic to appropriate destinations on the network. Identity access management is used for authenticating and authorizing users; it is not relevant to network controls between subnetworks. IP address tables are not a security control.

7. When you create a machine learning service to identify text in an image, what type of servers should you use to manage compute resources? - C. No servers; specialized services are serverless

- C. Option C is correct because specialized services in GCP are serverless. Google manages the compute resources used by the services. There is no need for a user to allocate or monitor VMs.

8. Investing in servers for extended periods of time, such as committing to use servers for three to five years, works well when? - B. A company can accurately predict server need for an extended period of time.

- B. Option B is correct; investing in servers works well when an organization can accurately predict the number of servers and other equipment it will need for an extended period and can utilize that equipment consistently. Startups are not established businesses with histories that can guide expected needs in three to five years. It does not matter if a budget is fixed or variable; investing in servers should be based on demand for server capacity.

9. Your company is based in X and will be running a virtual server for Y. What factor determines the unit per minute cost? - B. The characteristics of the server

- B. The characteristics of the server, such as the number of virtual servers, the amount of memory, and the region where you run the VM, influence the cost, so option B is correct. Time of day is not a factor, nor is the type of application you run on the VM.

10. You plan to use Cloud Vision to analyze images and extract text seen in the image. You plan to process between 1,000 and 2,500 images per hour. How many VMs should you allocate to meet peak demand? - D. None; Cloud Vision is a serverless service.

- D. Cloud Vision is one of GCP's specialized services. Users of the service do not need to configure any VMs to use the service.

11. You have to run a number of services to support an application. Which of the following is a good deployment model? - B. Use containers in a managed cluster

- B. Containers give the most flexibility for using the resources of a cluster efficiently and orchestration platforms reduce the operations overhead, which makes option B correct. Running in a single cluster is not recommended because if the server fails, all services will be down. Using two VMs with one read-only is not useful. Read-only servers are sometimes used with databases, but there was no mention of databases in the question. Using a small VM and upgrading when it is no longer able to keep up with the workload delivers poor quality service to users and should be avoided.

12. You have created a VM. Which of the following system administration operations are you allowed to perform on it? - D. All of the above

- D. All of the operations are available to a system administrator after creating a VM, so option D is correct.

13. Cloud Filestore is based on what file system technology? - A. Network File System (NFS)

- A. Option A is correct; Cloud Filestore is based on Network Filesystem (NFS), which is a distributed file management system. The other options are file systems supported by Linux but are not the foundation of Cloud Filestore.

14. When setting up a network in GCP, your network the resources in it are treated as what? - A. Virtual private cloud

- A. When you create a network, it is treated as a virtual private cloud, which makes option A correct. Resources are added to the VPC and are not accessible outside the VPC unless you explicitly configure them to be. A subdomain is related to web domains and not related to GCP network configuration. Clusters, such as Kubernetes clusters, may be in your network, but are not a characteristic of the network.

15. You need to store data for X and therefore you are using a cache for Y. How will the cache affect data retrieval? - D. Using a cache will reduce latency, since retrieving from a cache is faster than retrieving from SSDs or HDDs.

- D. Caches use memory, and that makes them the fastest storage type for reading data, so option D is right. Caches are data stores on the backend of distributed systems, not the clients. A cache would have no effect on client-side JavaScript execution. Caches do not store data in a cache if power is lost; the data would have to be reloaded. Caches can get out of sync with the system of truth because the system of truth could be updated, but the cache may not be updated. Caches have faster read times than SSDs and HDDs.

16. Why can cloud providers offer elastic resource allocation? - B. Extensive resources and the ability to quickly shift resources between customers enables public cloud providers to offer elastic resource allocation more efficiently than can be done in smaller data centers.

- B. Option B is correct; cloud providers have large capacity and can quickly allocate those resources to different customers. With a mix of customers and workloads, they can optimize the allocation of resources. Option A is incorrect; cloud providers do not take resources from one customer to give them to another, with the exception of preemptible instances. Option C is incorrect; cloud providers usually offer discounts for increased use.

17. What is not a characteristic of specialized services in Google Cloud Platform? - C. They require monitoring by the user.

- C. Specialized services are monitored by Google so users to not have to monitor them; therefore, option C is correct. Specialized services provide a specific compute functionality but do not require the user to configure any resources. They also provide APIs.

18. Your client's transactions must access a drive attached to a VM that allows for random access to parts of files. What kind of storage does the attached drive provide? - B. Block storage

- B. Attached drives are block storage devices. Cloud Storage is the object storage service and does not attach directly to a VM. NoSQL is a type of database, not a storage system. Attached drives may be either SSDs or hard drives.

19. You are deploying a new relational database to support a web application. Which type of storage system would you use to store data files of the database? - C. Block storage

- C. Databases require persistent storage on block devices. Object storage does not provide data block or file system storage, making option C the correct answer. Data storage is not a type of storage system. Caches are often used with databases to improve read performance, but they are volatile and not suitable for persistently storing data files.

20. A user prefers services that require minimal setup; why would you recommend Cloud Storage, App Engine, and Cloud Functions? - B. They are serverless.

- B. All three services are serverless, so the user does not need to configure VMs; therefore, option B is correct. Cloud Storage is charged based on time and size of data stored. App Engine Standard and Cloud Functions are not restricted to just the Go language.

### 2 Google Cloud Computing Services


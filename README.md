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

Computing Components of Google Cloud Platform

Computing Resources

"Users can choose the operating system, which packages to install, and when to back up and perform other maintenance operations."

"This type of computing service is typically referred to as infrastructure as a service (IaaS)."

"An alternative model is called platform as a service (PaaS), which provides a runtime environment to execute applications without the need to manage underlying servers, networks, and storage systems."

"GCP's IaaS computing product is called Compute Engine, and the PaaS offerings are App Engine and Cloud Functions."

"In addition, Google offers Kubernetes Engine, which is a service for managing containers in a cluster; this type of service is an increasingly popular alternative to managing individual sets of VMs."

Compute Engine

"Compute Engine is a service that allows users to create VMs, attach persistent storage to those VMs, and make use of other GCP services, such as Cloud Storage."

"GCP uses a security hardened version of the KVM hypervisor."

"KVM stands for Kernel Virtual Machine and provides virtualization on Linux machines running on x86 hardware."

"The last option, making a VM preemptible, means you may be charged significantly less for the VM than normal (around 80 percent less), but your VM could be shut down at any time by Google."

"It will frequently be shut down if the preemptible VM has run for at least 24 hours."

Kubernetes Engine

"Kubernetes Engine is designed to allow user to easily run containerized applications on a cluster of servers."

"Containers take a different approach than VMs for isolating computing processes."

"Another approach to isolating computing resources is to use features of the host operating system to isolate processes and resources."

"With this approach, there is no need for a hypervisor; the host operating system maintains isolation."

"In addition, Kubernetes monitors the health of servers in the cluster and automatically repairs problems, such as failed servers."

"Kubernetes Engine also supports autoscaling, so if the load on your applications increases, Kubernetes Engine will allocate additional resources."

App Engine

"App Engine manages the underlying computing and network infrastructure."

"In the standard environment, you run applications in a language-specific sandbox, so your application is isolated from the underlying server's operating system as well as from other applications running on that server."

"In the flexible environment, you run Docker containers in the App Engine environment."

"The flexible environment works well in cases where you have application code bu also need libraries or other third-party software installed."

Cloud Functions

"Cloud Functions runs code in response to an event, like a file being uploaded to Cloud Storage or a message being written to a message queue."

"The code that executes in the Cloud Functions environment must be short-running – this computing service is not designed to execute long-running code."

Storage Components of Google Cloud Platform

Storage Resources

"Sometimes an application needs fast read and write times for moderate amounts of data."

"Other times, a business application may need access to petabytes of archival storage but can tolerate minutes and even hours to retrieve a document."

Cloud Storage

"Cloud Storage is GCP's object storage system."

"Objects are organized into buckets, which are analogous to directories in a file system."

"It is a service that receives, stores, and retrieves files or objects from a distributed storage system."

"Cloud Storage is useful for storing objects that are treated as single units of data."

"A zone is considered a single failure domain, which means that if all instances of your application are running in a zone and there is a failure, then all instances of your application will be inaccessible."

"The cold storage class is low-cost archival storage designed for high durability and infrequent access."

"For example, you could define a policy that moves all objects more than 60 days old in a bucket to nearline storage or deletes any object in a coldline storage bucket that is older than five years."

Persistent Disk

"Persistent disks are a storage service that are attached to VMs in Compute Engine or Kubernetes Engine."

"SSDs cost more than HDDs, so applications that require large amounts of persistent disk storage but can tolerate longer read and write times can use HDDs to meet their storage requirements."

Cloud Storage for Firebase

Cloud Filestore

"Filestore can provide high numbers of input-output operations per second (IOPS) as well as variable storage capacity."

"Filestore implements the Network File System (NFS) protocol so system administrators can easily mount shared file systems on virtual servers."

Databases

"Some provide support for atomic transactions, and others are better suited for applications with less stringent consistency and transaction requirements."

Cloud SQL

"Cloud SQL is GCP's managed relational database service that allows users to set up MySQL or PostgreSQL databases on VMs without having to attend to database administration tasks, such as backing up databases or patching database software."

"First-generation MySQL databases use MySQL 5.5 or 5.6 and can have up to 16GB of RAM and 500GB of data storage."

"Second-generation MySQL databases use MySQL 5.6 or 5.7 and can have up to 416GB of RAM along with 10TB of data storage." 

"PostgreSQL 9.6 runs on the second-generation platform and can be configured with up to 64 CPUs, 416GB of RAM, and up to 10TB of storage."

"Cloud SQL PostgreSQL also supports common extensions such as PostGIS, cubes for analytic processing, and hstore for storing key-value pairs in a single PostgreSQL value."

Cloud Bigtable

"Cloud Bigtable is designed for petabyte-scale applications that can manage up to billions of rows and thousands of columns."

"It is based on a NoSQL model known as a wide-column data model, and unlike Cloud SQL that supports relational databases."

"Bigtable is suited for applications that require low-latency write and read operations."

"Bigtable integrates with other Google Cloud services, such as Cloud Storage, Cloud Pub/Sub, Cloud Dataflow, and Cloud Dataproc."

Cloud Spanner

"Cloud Spanner is Google's globally distributed relational database that combines the key benefits of relational databases, such as strong consistency and transactions, with the ability to scale horizontally like a NoSQL database."

Cloud Datastore

"Cloud Datastore is a NoSQL document database."

"Cloud Datastore is accessed via a REST API that can be used from applications running in Compute Engine, Kubernetes Engine, or App Engine."

"It will also shard, or partition, data as needed to maintain performance."

"Cloud Datastore is well suited to applications that demand high scalability and structured data and do not always need strong consistency when reading data."

Cloud Memorystore

"Other databases offered in GCP are designed to store large volumes of data and support complex queries, but Cloud Memorystore is a managed Redis service for caching frequently used data in memory."

Cloud Firestore

"Cloud Firestore is another GCP-managed NoSQL database service designed as a backend for highly scalable web and mobile applications."

"A distinguishing feature of Cloud Firestore is its client libraries that provide offline support, synchronization, and other features for managing data across mobile devices, IoT devices, and backend data stores."

"For example, applications on mobile devices can be updated in real time as data in the backend changes."

Networking Components of Google Cloud Platform

Networking Services

Virtual Private Cloud

"Although multiple enterprises will use the same cloud infrastructure, each enterprise can logically isolate its cloud resources by creating a virtual private cloud (VPC)."

"A distinguishing feature of GCP is that a VPC can span the globe without relying on the public Internet."

"Traffic from any server on a VPC can be securely routed through the Google global network to any other point on that network."

"Another advantage of the Google network structure is that your backend servers can access Google services, such as machine learning or IoT services, without creating a public IP address for backend servers."

Cloud Load Balancing

"Using a single multicast IP address, Cloud Load Balancing can distribute the workload within and across regions, adapt to failed or degraded servers, and autoscale your compute resources to accommodate changes in workload."

Cloud Armor

"Cloud Armor is a Google network security service that builds on the Global HTTP(s) Load Balancing service."

"Cloud Armor features include the following: ability to allow or restrict access based on IP address, predefined rules to counter cross-site scripting attacks, ability to counter SQL injection attacks, ability to define rules at both level 3 (network) and level 7 (application), allows and restricts access based on the geolocation of incoming traffic."

Cloud CDN

"With content delivery networks (CDNs), users anywhere can request content from systems distributed in various regions."

"CDNs enable low-latency response to these requests by caching content on a set of endpoints across the globe."

"CDNs are especially important for sites with large amounts of static content and a global audience."

Cloud Interconnect

"Interconnect with direct access to networks uses the Address Allocation for Private Internets standard (RFC 1918) to connect to devices in your VPC."

"A direct network connection is maintained between an on-premise or hosted data center and one of Google's colocation facilities, which are located in North America, South America, Europe, Asia, and Australia."

"Alternatively, if an organization cannot achieve a direct interconnect with a Google facility, it could use Partner Interconnect."

"For organizations that do not require the bandwidth of a direct or peered interconnect, Google offers VPN services that enable traffic to transmit between data centers and Google facilities using the public Internet."

Cloud DNS

Identity Management

"Users often need similar sets of permissions."

"Someone who has the ability to create a VM will likely want to be able to modify or delete those VMs."

"Groups of related permissions can be bundled into roles."

"Roles are sets of permissions that can be assigned to an identity."

Development Tools

"Cloud SDK is a command-line interface for managing GCP resources, including VMs, disk storage, network firewalls, and virtually any other resource you might deploy in GCP."

Additional Components of Google Cloud Platform

Management Tools

Stackdriver

"This is a service that collects metrics, logs, and event data from applications and infrastructure and integrates the data so DevOps engineers can monitor, assess, and diagnose operational problems."

Monitoring

Logging

Error Reporting

Trace

Debugger

Profiler

Specialized Services

Apigee API Platform

"The Apigee platform allows developers to deploy, monitor, and secure their APIs."

Data Analytics

AI and Machine Learning

Cloud AutoML

Cloud Machine Learning Engine

Cloud Natural Language Processing

Cloud Vision

Exam Essentials

"Understand the difference between Compute Engine, Kubernetes Engine, App Engine, and Cloud Functions."

"Understand what is meant by serverless."

"Understand the difference between object and file storage."

"Know the different kinds of databases."

"Understand virtual private clouds."

"Understand load balancing."

"Understand developer and management tools."

"Know the types of specialized services offered by Google Cloud Platform."

"Know the main differences between on-premises and public cloud computing."

Review Questions

1. You are planning to deploy a SaaS application for customers in North America, Europe, and Asia. To maintain scalability, you will need to distribute workload across servers in multiple regions. Which GCP service would you use to implement the workload distribution? - C. Cloud Load Balancing

- C. Cloud Load Balancing distributes workloads within and across regions, provides health checks, and implements autoscaling. Cloud DNS provides domain name services, such as translating a URL like www.example.com to an IP address. Cloud Spanner is a distributed relational database but does not implement workload distribution. Cloud CDN distributes content across regions to reduce latency when delivering content to users across the globe.

2. You have decided to deploy a set of microservices using containers. You could install and manage Docker on Compute Engine instances, but you'd rather have GCP provide some container management services. Which two GCP services allow you to run containers in a managed service? - C. Kubernetes Engine and App Engine flexible environment

- C. App Engine flexible environments allow you to run containers on the App Engine PaaS. Kubernetes Engine is an orchestration platform for running containers. Both provide container management services. The App Engine standard environment runs applications in language-specific sandboxes and is not a general container management system. Cloud Functions is a serverless service for running code in response to events. It does not provide container services.

3. Why would an API developer want to use the Apigee API platform? - D. A and B

- D. Options A and B are both correct answers. The Apigee API platform provides policy-based rate-limiting and routing services to help accommodate spikes in traffic. It also provides OAuth 2.0 and SAML authentication. It does not provide version control; Cloud Source Repositories is the service used for version control.

4. You are deploying an API to the public Internet and are concerned that your service will be subject to DDoS attacks. Which GCP service should you consider to protect your API? - A. Cloud Armor

- A. Cloud Armor builds on GCP's load balancing services to provide the ability to allow or restrict access based on IP address, deploy rules to counter cross-site scripting attacks, and provide countermeasures to SQL injection attacks. Cloud CDN is a content distribution service, not a security service. Identity Access Management is a security service, but it is for authentication and authorization, not denial-of-service mitigation. Virtual private clouds are used to restrict network access to an organization's resources, but it does not have features to mitigate denial-of-service attacks. Also, Cloud CDN acts as a first line of defense in the case of DDoS attacks.

5. You have an application that uses a Pub/Sub message queue to maintain a list of tasks that are to be processed by another application. The application that consumes messages from the Pub/Sub queue removes the message only after completing the task. It takes approximately 10 seconds to complete a task. It is not a problem if two or more VMs perform the same task. What is a cost-effective configuration for processing this workload? - A. Use preemptible VMs

- A. This is a good use case for preemptible VMs because they could reduce the cost of running the second application without the risk of losing work. Since tasks are deleted from the queue only after they are completed if a preemptible VM is shut down before completing the task, another VM can perform the task. Also, there is no harm in running a task more than once, so if two VMs do the same task, it will not adversely affect the output of the application. Dataproc and Spanner are not appropriate products for this task.

6. Your department is deploying an application that has a database backend. You are concerned about the read load on the database server and want to have data available in memory to reduce the time to respond to queries and to reduce the load on the database server. Which GCP service would you use to keep data in memory? - B. Cloud Memorystore

- B. Cloud Memorystore is the only GCP service designed to cache data in memory. Cloud SQL is a relational database service and might be a good option for the backend database. Cloud Spanner is a global relational database and is a good option when you need a globally consistent database. Cloud Datastore is a document database suitable for product catalogs, user profiles, and other semistructured data.

7. The Cloud SDK can be used to configure and manage resources in which of the following services? - D. All of the above

- D. All three of the services listed, Compute Engine, Cloud Storage, and network firewalls, can be managed and configured using Cloud SDK.

8. What server configuration is required to use Cloud Functions? - D. None

- D. Cloud Functions is a serverless product, no configuration is required.

9. You have been assigned the task of consolidating log data generated by each instance of an application. Which of the Stackdriver management tools would you use? - D. Logging

- D. The Stackdriver Logging product is used to consolidate and manage logs generated by applications and servers.

10. Which specialized services are most likely to be used to build a data warehousing platform that requires complex extraction, transformation, and loading operations on batch data as well as processing streaming data? - B. Data analytics

- B. The data analytics set of specialized services includes products that help with extraction, transformation, and loading (ETL) and work with both batch and streaming data. The Apigee API platform is used for managing APIs and does not meet the needs described. AI and machine learning might be useful for analyzing data in the data warehouse, but the services in that set are not always helpful for ETL operations. Cloud SDK is used to control services but by itself is not directly able to perform the operations needed.

11. Your company has deployed 100,000 Internet of Things (IoT) sensors to collect data on the state of equipment in several factories. Each sensor will collect and send data to a data store every 5 seconds. Sensors will run continuously. Daily reports will produce data on the maximum, minimum, and average value for each metric collected on each sensor. There is no need to support transactions in this application. Which database product would you recommend? - B. Cloud Bigtable

- B. Bigtable is designed to accept billions of rows of data. Collecting data from 100,000 sensors every 5 seconds will generate 6,000,000 data points every minute, or 8,640,000,000 data points per day. Spanner is a relational database and supports transactions, but they are not needed. Cloud SQL MySQL and Cloud SQL PostgreSQL would be difficult to scale to this level of read and write performance.

12. You are the lead developer on a medical application that uses patients' smartphones to capture biometric data. The app is required to collect data and store it on the smartphone when data cannot be reliably transmitted to the backend application. You want to minimize the amount of development you have to do to keep data synchronized between smartphones and backend data stores. Which data store option should you recommend? - A. Cloud Firestore

- A. Cloud Firestore is a mobile database service that can synchronize data between mobile devices and centralized storage. Spanner is a global relational database for large-scale applications that require  transaction support in highly scaled databases. Datastore and Cloud SQL could be used but would require more custom development to synchronize data between mobile devices and the centralized data store.

13. A software engineer comes to you for a recommendation. She has implemented a machine learning algorithm to identify cancerous cells in medical images. The algorithm is computationally intensive, makes many mathematical calculations, requires immediate access to large amounts of data, and cannot be easily distributed over multiple servers. What kind of Compute Engine configuration would you recommend? - B. High memory, high CPU, GPU

- B. A computationally intensive application obviously requires high CPUs, but the fact that there are many mathematical calculations indicates that a GPU should be used. You might consider running this in a cluster, but the work is not easily distributed over multiple servers, so you will need to have a single server capable of handling the load. Immediate access to large amounts of data indicates that a high-memory machine should be recommended.

14. You are tasked with mapping the authentication and authorization policies of your on-premises applications to GCP's authentication and authorization mechanisms. The GCP documentation states that an identity must be authenticated in order to grant privileges to that identity. What does the term identity refer to? - C. Role

- B. Identities are abstractions of users. They can also represent characteristics of processes that run on behalf of a human user or a VM in the GCP. Identities are not related to VM IDs. Roles are collections of privileges that can be granted to identities. Option D is synonymous with option C.

15. A client is developing an application that will need to analyze large volumes of text information. The client is not expert in text mining or working with language. What GCP service would you recommend they use? - C. Cloud Natural Language Processing

- C. Cloud Natural Language Processing provides functionality for analyzing text. Cloud Text Miner does not exist. Cloud ML is a general-purpose machine learning service that could be applied to text analysis but would require knowledge of language processing, which the client does not have. Cloud Vision is for image processing.

16. Data scientists in your company want to use a machine learning library available only in Apache Spark. They want to minimize the amount of administration and DevOps work. How would you recommend they proceed? - B. Use Cloud Dataproc

- B. Both options B and D would meet the need of running Spark, which would give the data scientists access to the machine learning library they need. However, option D requires that they manage and monitor the cluster of servers, which would require more DevOps and administration work than if they used the Dataproc service. Option C, BigQuery, is a scalable database, not a platform for running Spark. Cloud Spark is a fictitious product and does not exist in the GCP.

17. Database designers at your company are debating the best way to move a database to GCP. The database supports an application with a global user base. Users expect support for transactions and the ability to query data using commonly used query tools. The database designers decide that any database service they choose will need to support ANSI 2011 and global transactions. Which database service would you recommend? - B. Cloud Spanner

- B. Option B is correct. Spanner supports ANSI 2011 standard SQL and global transactions. Cloud SQL supports standard SQL but does not have global transaction. Datastore and Bigtable are NoSQL databases.

18. Which specialized service supports both batch and stream processing workflows? - A. Cloud Dataproc

- A. Dataproc is designed to execute workflows in both batch and streaming modes, which makes option A correct. BigQuery is a data warehouse service. Datastore is a document database. AutoML is a machine learning service.

19. You have a Python application you'd like to run in a scalable environment with the least amount of management overhead. Which GCP product would you select? - C. App Engine standard environment

- C. App Engine standard environment provides a serverless Python sandbox that scales automatically, so option C is correct. App Engine flexible environment runs containers and requires more configuration. Cloud Engine and Kubernetes Engine both require significant management and monitoring.

20. A product manager at your company reports that customers are complaining about the reliability of one of your applications. The application is crashing periodically, but developers have not found a common pattern that triggers the crashes. They are concerned that they do not have good insight into the behavior of the application and want to perform a detailed review of all crash data. Which Stackdriver tool would you use to view consolidated crash information? - D. Error Reporting

- D. Error Reporting consolidates crash information, which makes Error Reporting the right answer. Monitoring collects metrics on application and server performance. Logging is a log management service. Dataproc is not part of Stackdriver; it is a managed Hadoop and Spark service.

### 3 Projects, Service Accounts, and Billing

How GCP Organizes Projects and Accounts

GCP Resource Hierarchy

Organization

"An organization is the root of the resource hierarchy and typically corresponds to a company or organization."

"A single cloud identity is associated with at most one organization."

"Cloud identities have super admins, and those super admins assign the Organization Administrator Identity and Access Management (IAM) role to users who manage the organization."

Folder

"Folders are the building blocks of multilayer organizational hierarchies."

"Folders can contain other folders or projects."

Project

"Your organization will have a quota of projects it can create."

Organization Policies

"One way to think of the difference is that IAM specifies who can do things, and the Organization Policy Service specifies what can be done with resources."

Constraints on Resources

"List constraints are lists of values that are allowed or disallowed for a resource."

"Boolean constraints evaluate to true or false and determine whether the constraint is applied or not."

Policy Evaluation

"A better approach is to define a policy that constrains what can be done and attach that policy to an object in the resource hierarchy."

"For example, since InfoSec wants all VMs to disable serial port access, you could specify a policy that constrains serial port access and then attach it to the organization."

"All folders and projects below the organization will inherit that policy."

Managing Projects

Roles and Identities

Roles in GCP

"A role is a collection of permissions."

"Roles are granted to users by binding a user to a role."

"When we talk of identities, we mean the record we use to represent a human user or service account in GCP."

"Primitive roles include Owner, Editor, and Viewer."

"By using predefined roles, you can grant only the permissions a user needs to perform their function."

Granting Roles to Identities

Service Accounts

"For example, you may have an application that needs to access a database, but you do not want to allow users of the application to access the database directly."

"That service account can be assigned to the application so the application can execute queries on behalf of users without having to grant database access to those users."

"When we assign a role to a service account, we are treating it as an identity."

"When we give users permission to access a service account, we are treating it as a resource."

"Users can create up to 100 service accounts per project."

"Service accounts can be managed as a group of accounts at the project level or at the individual service account level."

"Service accounts are created automatically when resources are created."

Billing

Billing Accounts

"All projects must have a billing account unless they only use free services."

"Few users will likely have Billing Account Creator, and those who do will likely have a financial role in the organization."

"Cloud admins may have Billing Account Administrator to manage the accounts."

"Any user who can create a project should have Billing Account User so new projects can be linked to the appropriate billing account."

"Billing Account Viewer is useful for some, like an auditor who needs to be able to read billing account information but not change it."

Billing Budgets and Alerts

"By default, three percentages are set: 50 percent, 90 percent, and 100 percent."

Exporting Billing Data

Enabling APIs

"GCP uses APIs to make services programatically accessible."

"To enable service APIs, you can select APIs & Services from the main console menu."

Provisioning Stackdriver Workspaces

"For monitoring and logging data to be saved into Stackdriver, you need to create a workspace to save it."

Exam Essentials

"Understand the GCP resource hierarchy."

"Understand organization policies."

"Understand service accounts and how they are used."

"Understand GCP Billing."

"Know how to enable APIs and create Stackdriver Workspaces."

Review Questions

1. You are designing cloud applications for a healthcare provider. The records management application will manage medical information for patients. Access to this data is limited to a small number of employees. The billing department application will have insurance and payment information. Another group of employees will have access to billing information. In addition, the billing system will have two components: a private insurance billing system and a government payer billing system. Government regulations require that software used to bill the government must be isolated from other software systems. Which of the following resource hierarchies would meet these requirements and provide the most flexibility to adapt to changing requirements? - A. One organization, with folders for records management and billing. The billing folder would have private insurer and government payer folders within it. Common constraints would be specified in organization-level policies. Other policies would be defined at the appropriate folder.

- A. Option A, the correct answer, separates the two main applications into their own folders and further allows separating private insurance from government payer, but using folders for each. This satisfies the regulatory need to keep the government payer software isolated from other software. Option B does not include an organization, which is the root of the resource hierarchy. Option C is not flexible with regard to differences in constraints on different applications. Option D is false because option A does meet the requirements.

2. When you create a hierarchy, you can have more than one of which structure? - C. Folder and project

- C. Resource hierarchies have a single organization at the root, which makes option C correct. Below that, there are folders that can contain other folders or projects. Folders can contain multiple folders and multiple projects.

3. You are designing an application that uses a series of services to transform data from its original form into a format suitable for use in a data warehouse. Your transformation application will write to the message queue as it processes each input file. You don't want to give users permission to write to the message queue. You could allow the application to write to the message queue by using which of the following? - B. Service account

- B. Service accounts are designed to give applications or VMs permission to perform tasks. Billing accounts are for associating charges with a payment method. Folders are part of resource hierarchies and have nothing to do with enabling an application to perform a task. Messaging accounts are a fictitious option.

4. Your company has a number of policies that need to be enforced for all projects. You decide to apply policies to the resource hierarchy. Not long after you apply the policies, an engineer finds that an application that had worked prior to implementing policies is no longer working. The engineer would like you to create an exception for the application. How can you override a policy inherited from another entity in the resource hierarchy? - A. Inherited policies can be overridden by defining a policy at a folder or project level.

- A. Inherited policies can be overridden by defining a policy at a folder or project level. Service accounts and billing accounts are not part of the resource hierarchy and are not involved in overriding policies.

5. Constraints are used in resource hierarchy policies. Which of the following are types of constraints allowed? - E. All of the above

- E. All of the listed types of constraints are supported in policies.

6. A team with four members needs you to set up a project that needs only general permissions for all resources. You are granting each person a primitive role for different levels of access, depending on their responsibilities in the project. Which of the following are not included as primitive roles in Google Cloud Platform? - B. Publisher

- B. Option B is the correct answer because Publisher is not a primitive role. Owner, Editor, and Viewer are the three primitive privileges in GCP.

7. You are deploying a new custom application and want to delegate some administration tasks to DevOps engineers. They do not need all the privileges of a full application administrator, but they do need a subset of those privileges. What kind of role should you use to grant those privileges? - D. Custom

- D. Primitive roles only include the Owner, Editor, and View permissions. Predefined roles are designed for GCP products and services, like App Engine or BigQuery. For a custom application, you can create sets of privileges that give the user with that role as much permission as needed but not more.

8. An app for a finance company needs access to a database and a Cloud Storage bucket. There is no predefined role that grants all the needed permissions without granting some permissions that are not needed. You decide to create a custom role. When defining custom roles, you should follow which of the following principles? - D. Least privilege

- D. Users should have only the privileges that are needed to carry out their duties. This is the principle of least privilege. Rotation of duties is another security principle related to having different people perform a task at different times. Defense in depth is the practice of using multiple security controls to protect the same asset. Option B is not a real security principle.

9. How many organizations can you create in a resource hierarchy? - A. 1

- A. A resource hierarchy has only one organization, which makes option A correct. You can however, create multiple folders and projects within a resource hierarchy.

10. You are contacted by the finance department of your company for advice on how to automate payments for GCP services. What kind of account would you recommend setting up? - B. Billing account

- B. In option B, the correct answer, the billing account is used to specify payment information and should be used to set up automatic payments. Service accounts are used to grant privileges to a VM and are not related to billing and payments. Resource accounts and credit accounts do not exist.

11. You are experimenting with GCP for your company. You do not have permission to incur costs. How can you experiment with GCP without incurring charges? - C. You can use only free services in GCP.

- C. GCP offers a free service level for many products, which makes option C the correct answer. You can use these services without having to set up a billing account. Google charges for serverless products, such as Cloud Functions and App Engine, when customers exceed the amount allowed under the free tier.

12. Your DevOps team has decided to use Stackdriver monitoring and logging. You have been asked to set up Stackdriver workspaces. When you set up a Stackdriver workspace, what kind of resource is it associated with? - D. A project

- D. Stackdriver workspaces are linked to projects, not individual resources like VM instances, clusters, or App Engine apps, so option D is correct. Options A, B, and C all incorrectly indicate that Workspaces are associated with individual compute resources.

13. A large enterprise is planning to use GCP across a number of subdivisions. Each subdivision is managed independently and has its own budget. Most subdivisions plan to spend tens of thousands of dollars per month. How would you recommend that they set up their billing account(s)? - B. Use multiple self-service billing accounts.

- D. Large enterprises should use invoicing when incurring large charges, which makes option D the right answer. A self-service account is appropriate only for amounts that are within the credit limits of credit cards. Since the subdivisions are independently managed and have their own budgets, each should have its own billing accounts.

14. An application administrator is responsible for managing all resources in a project. She wants to delegate responsibility for several service accounts to another administrator. If additional service accounts are created, the other administrator should manage those as well. What is the best way to delegate privileges needed to manage the service accounts? - A. Grant `iam.serviceAccountUser` to the administrator at the project level.

- A. When a user is granted `iam.serviceAccountUser` at the project level, that user can manage all service accounts in the project, so option A is correct. If a new service account is created, they will automatically have privilege to manage that service account. You could grant `iam.serviceAccountUser` to the administrator at the service account level, but that would require setting the role for all service accounts. If a new service account is created, the application administrator would have to grant `iam.serviceAccountUser` to the other administrator on the new service account. `iam.serviceProjectAccountUser` is a fictional role. 

15. You work for a retailer with a large number of brick and mortar stores. Every night the stores upload daily sales data. You have been tasked with creating a service that verifies the uploads every night. You decide to use a service account. Your manager questions the security of your proposed solution, particularly about authenticating the service account. You explain the authentication mechanism used by service accounts. What authentication mechanism is used? - C. Encrypted keys

- C. When a service account is created, Google generates encrypted keys for authentication, making option C correct. Usernames and passwords are not an option for service accounts. Two-factor authentication is an authentication practice that requires two forms of authentication, such as a username password pair and a code from an authentication device. Biometrics cannot be used by services and is not an option.

16. What objects in GCP are sometimes treated as resources and sometimes as identities? - D. Roles

- B. Service accounts are resources that are managed by administrators, but they also function as identities that can be assigned roles, which makes option B the correct answer. Billing accounts are not related to identities. Projects are not identities; they cannot take on roles. Roles are resources but not identities. They can take on privileges, but those privileges are used only when they are attached to an identity.

17. You plan to develop a web application using products from the GCP that already include established roles for managing permissions such as read-only access or the ability to delete the old version. Which of the following roles offers these capabilities? - B. Predefined roles

- B. Predefined roles are defined for a particular product, such as App Engine or Compute Engine, so option B is the right answer. They bundle privileges often needed together when managing or using a service. Primitive roles are building blocks for other roles. Custom roles are created by users to meet their particular needs; Application roles is a fictitious role.

18. You are reviewing a new GCP account created for use by the finance department. An auditor has questions about who can create projects by default. You explain who has privileges to create projects by default. Who is included? - D. Only billing account users.

- B. By default all users in an organization can create projects, which makes option B correct. The role `resourcemanager.projects.create` is the role that allows users to create projects. The billing account is not associated with creating projects.

19. How many projects can be created in an account? - D. Each account has a limit determined by Google.

- D. The maximum number of organizations is determined on a per-account basis by Google, so option D is the correct answer. If you need additional organizations, you can contact Google and ask for an increase in your limit.

20. You are planning how to grant privileges to users of your company's GCP account. You need to document what each user will be able to do. Auditors are most concerned about a role called Organization IAM roles. You explain that users with that role can perform a number of tasks, which include all of the following except which one? - A. Defining the structure of the resource hierarchy

- B. Users with the Organization IAM role are not necessarily responsible for determining what privileges should be assigned to users. That is determined based on the person's role in the organization and the security policies established within the organization, which makes option B correct. 

### 4 Introduction to Computing in Google Cloud


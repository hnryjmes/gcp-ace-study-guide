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

Compute Engine

Virtual Machine Images

"Instances run images, which contain operating systems, libraries, and other code."

"The public images include a range of operating systems, such as CentOS, Container Optimized OS from Google, Debian, Red Hat Enterprise Linux, SUSE Enterprise Linux Server, Ubuntu, and Windows Server."

"Custom images are especially useful if you have to configure an operation system and install additional software on each instance of a VM that you run."

"Instead of repeatedly configuring and installing software for each instance, you could configure and install once and then create a custom image from the boot disk of the instance."

"You can import such an image using the virtual disk import tool provided by Google."

Virtual Machines Are Contained in Projects

Virtual Machines Run in a Zone and Region

"Zones are data center-like resources, but they be comprised of one or more closely coupled data centers."

Users Need Privileges to Create Virtual Machines

Compute Engine Admin

Compute Engine Network Admin

Compute Engine Security Admin

Compute Engine Viewer

Preemptible Virtual Machines

"Preemptible VMs are short-lived compute instances suitable for running certain types of workloads – particularly for applications that perform financial modeling, rendering, big data, continuous integration, and web crawling operations."

"If an application is fault-tolerant and can withstand possible instance interruptions (with a 30 second warning), then using preemptible VM instances can reduce Google Compute Engine costs significantly."

"Some big data analysis jobs run on clusters of servers running software like Hadoop and Spark."

"If a node goes down in the middle of a job, the platform detects the failure and moves workload to other nodes in the server."

Limitations of Preemptible Virtual Machines

"May terminate at any time. If they terminate within 10 minutes of starting, you will not be charged for that time."

Custom Machine Types

"Compute Engine has more than 25 predefined machine types grouped into standard types, high-memory machines, high-CPU machines, shared core type, and memory-optimized machines."

"The predefine options for VMs will meet the needs of many use cases, but there may be times where your workload could run more cost effectively and faster on a configuration that is not already defined."

Use Cases for Compute Engine Virtual Machines

App Engine

"Instead of configuring VMs, you specify some basic resource requirements along with your application code, and Google will manage the resources needed to run the code."

Structure of an App Engine Application

"The number of instances used to provide an application defends on your configuration for the application and the current load on the application."

App Engine Standard and Flexible Environments

App Engine Standard Environment

"With the second-generation standard environment, developers can use any language extension, but in the first generation only a select set of whitelisted extensions and libraries are allowed."

"Network access is restricted in the first generation, but users have full network access in the second generation."

App Engine Flexible Environment

"The flexible environment uses Docker containers, so developers familiar with Docker files can specify base operating system images, additional libraries and tools, and custom tools"

Use Cases for App Engine

"The App Engine product is a good choice for a computing platform when you have little need to configure and control the underlying operating system or storage system."

When to Use App Engine Standard Environment

"The standard environment provides a language-specific runtime that comes with its own constraints."

When to Use App Engine Flexible Environment

"The App Engine flexible environment is well suited for applications that can be decomposed into services and where each service can be containerized."

Kubernetes Engine

Kubernetes Functionality

"Kubernetes is designed to support clusters that run a variety of applications."

Kubernetes Cluster Architecture

"A Kubernetes cluster includes a cluster master node and one or more worker nodes."

"Cluster services, such as the Kubernetes API server, resource controllers, and schedulers, run on the master."

"The master determines what containers and workloads are run on each node."

"Kubernetes deploys containers in groups called pods."

"Containers within a single pod share storage and network resources."

"Containers within a pod share an IP address and port space."

Kubernetes High Availability

"One way Kubernetes maintains cluster health is by shutting down pods that become starved for resources."

"Kubernetes supports something called eviction policies that set thresholds for resources."

"When a resource is consumed beyond the threshold, then Kubernetes will start shutting down pods."

"Another way Kubernetes provides for high reliability is by running multiple identical pods."

"The identical pods are referred to as replicas."

Kubernetes Engine Use Cases

"Kubernetes Engine supports the concept of pods and deployments sets, which allow application developers and administrators to manage services as a logical unit."

"This can help if you have a set of services that support a user interface, another set that implements business logic, and a third set that provides backend services."

Cloud Functions

"Cloud functions provides the “glue” between services that are otherwise independent."

Cloud Functions Execution Environment

"The execution of one function is independent of all others. The lifecycles of Cloud Functions are not dependent on each other."

"Since each invocation of a Cloud Function runs in a separate instance, functions do not share memory or variables."

"In general, this means that Cloud Functions should be stateless."

Cloud Functions Use Cases

"Asynchronous workflows in which each step starts at some time after the previous steps completes, but there are no assumptions about when the processing steps will complete."

Summary

"Loosely coupled applications may be strung together to implement complex workflows."

Exam Essentials

"Understand how images are used to create instances of VMs and how VMs are organized in projects."

"Know that GCP has multiple geographic regions and regions have one or more zones."

"Understand what preemptible VMs are and when they are appropriate to use."

"Understand the difference between the App Engine standard and flexible environments."

"Know that Kubernetes is a container orchestration platform."

"Understand Kubernetes."

"Understand Cloud Functions."

Review Questions

1. You are deploying a Python web application to GCP. The application uses only custom code and basic Python libraries. You expect to have sporadic use of the application for the foreseeable future and want to minimize both the cost of running the application and the DevOps overhead of managing the application. Which computing service is the best option for running the application? - B. App Engine standard environment

- B. The App Engine standard environment can run Python applications, which can autoscale down to no instances when there is no load and thereby minimize costs. Compute Engine and the App Engine flexible environment both require more configuration management than the App Engine standard environment. Kubernetes Engine is used when a cluster of servers is needed to support large or multiple applications using the same computing resources.

2. Your manager is concerned about the rate at which the department is spending on cloud services. You suggest that your team use preemptible VMs for all of the following except which one? - A. Database server

- A. Database servers require high availability to respond to queries from users or applications. Preemptible machines are guaranteed to shut down in at most 24 hours. A batch processing job with no fixed time requirements could use preemptible machines as long as the VM is restarted. High-performance computing clusters can use preemptible machines because work on a preemptible machine can be automatically rescheduled for another node on the cluster when a server is preempted. D is incorrect because there is a correct answer in the set of options.

3. What parameters need to be specified when creating a VM in Compute Engine? - A. Project and zone

- A. VMs are created in projects, which are part of the resource hierarchy. They are also located in geographic regions and data centers, so a zone is specified as well. Usernames and admin roles are not specified during creation. The billing account is tied to a project and so does not have to be specified when the VM is created. Cloud storage buckets are created independently of VMs. Not all VMs will make use of storage buckets.

4. Your company has licensed a third-party software package that runs on Linux. You will run multiple instances of the software in a Docker container. Which of the following GCP services could you use to deploy this software package? - C. Compute Engine, Kubernetes Engine, and the App Engine flexible environment only

- C. Compute Engine can run Docker containers if you install Docker on the VM. Kubernetes and the App Engine flexible environment support Docker containers. The App Engine standard environment provides language-specific runtime environments and does not allow customers to specify custom Docker images for use.

5. You can specify packages to install into a Docker container by including commands in which file? - B. Dockerfile

- B. The name of the file that is used to build and configure a Docker container is Dockerfile.

6. How much memory of a node does Kubernetes require as overhead? - D. A scaled amount starting at 25 percent of memory and decreasing to 2 percent of marginal memory as the total amount of memory increases.

- D. Kubernetes uses 25 percent of memory up to 4GB and then slightly less for the next 4GB, and it continues to reduce the percentage of additional memory down to 2 percent of memory over 128GB.

7. Your manager is making a presentation to executives in your company advocating that you start using Kubernetes Engine. You suggest that the manager highlight all the features Kubernetes provides to reduce the workload on DevOps engineers. You describe several features, including all of the following except which one? - B. Security scanning for vulnerabilities

- B. Kubernetes provides load balancing, scaling, and automatic upgrading of software. It does not provide vulnerability scanning. GCP does have a Cloud Security Scanner product, but that is designed to work with App Engine to identify common application vulnerabilities.

8. Your company is about to release a new online service that builds on a new user interface experience driven by a set of services that will run on your servers. There is a separate set of services that manage authentication and authorization. A data store set of services keeps track of account information. All three sets of services must be highly reliable and scale to meet demand. Which of the GCP services is the best option for deploying this? - D. Kubernetes Engine

- D. The scenario described is a good fit for Kubernetes. Each of the groups of services can be structured in pods and deployed using Kubernetes deployment. Kubernetes Engine manages node health, load balancing, and scaling. App Engine standard environment has language-specific sandboxes and is not a good fit for this use case. Cloud Functions is designed for short-running event processing and is not the kind of continuous processing needed in this scenario. Compute Engine could meet the requirements of this use case, but it would require more effort on the part of application administrators and DevOps professionals to configure load balancers, monitor health, and manage software deployments.

9. A mobile application uploads images for analysis, including identifying objects in the image and extracting text that may be embedded in the image. A third party has created the mobile application, and you have developed the image analysis service. You both agree to use Cloud Storage to store images. You want to keep the two services completely decoupled, but you need a way to invoke the image analysis as soon as an image is uploaded. How should this be done? - B. Write a function in Python that is invoked by Cloud Functions when a new image file is written to the Cloud Storage bucket that receives new images. The function should submit the URL of the uploaded file to the image analysis service. The image analysis service will then load the image from Cloud Storage, perform analysis, and generate results, which can be saved to Cloud Storage.

- B. This is an ideal use case for Cloud Functions. The cloud function is triggered by a file upload event. The  cloud function calls the image processing service. With this setup, the two services are independent. No additional servers are required. Option A violates the requirement to keep the services independent. Options C and D incur more management overhead and will probably cost more to operate than option B.

10. Your team is developing a new pipeline to analyze a stream of data from sensors on manufacturing devices. The old pipeline occasionally corrupted data because parallel threads overwrote data written by other threads. You decide to use Cloud Functions as part of the pipeline. As a developer of a Cloud Function, what do you have to do to prevent multiple invocations of the function from interfering with each other? - D. Nothing. GCP ensures that function invocations do not interfere with each other.

- D. Each invocation of a cloud function runs in a secure, isolated runtime environment. There is no need to check whether other invocations are running. With the Cloud Functions service, there is no way for a developer to control code execution at the process or thread level.

11. A client of yours processes personal and health information for hospitals. All health information needs to be protected according to government regulations. Your client wants to move their application to Google Cloud but wants to use the encryption library that they have used in the past. You suggest that all VMs running the application have the encryption library installed. Which kind of image would you use for that? - A. Custom image

- A. You would create a custom image after you installed the custom code, in this case the encryption library. A public image does not contain custom code, but it could be used as the base that you add custom code to. Both CentOS and Ubuntu are Linux distributions. You could use either as the base image that you add custom code to, but on their own, they do not have custom code.

12. What is the lowest level of the resource hierarchy? - D. VM instance

- B. Projects are the lowest level of the resource hierarchy. The organization is at the top of the hierarchy, and folders are between the organization and projects. VM instances are not part of the resource hierarchy.

13. Your company is seeing a marked increase in the rate of customer growth in Europe. Latency is becoming an issue because your application is running in us-central1. You suggest deploying your services to a region in Europe. You have several choices. You should consider all of the following factors except which one? - D. Reliability

- D. All Google regions have the same level of service level agreement, so reliability is the same. Costs may differ between regions. Regulations may require that data stay within a geographic area, such as the European Union. Latency is a consideration when you want a region that is close to end users or data you will need is already stored in a particular region.

14. What role gives users full control over Compute Engine instances? - B. Compute Admin role

- B. Compute Engine Admin Role is the role that gives users complete control over instances. Options A and C are fictitious roles. Compute Engine Security Admin gives users the privileges to create modify, and delete SSL certificates and firewall rules.

15. Which of the following are limitations of a preemptible VM? - D. All of the above

- D. Preemptible VMs will be terminated after 24 hours. Google does not guarantee that preemptible VMs will be available. Once an instance is started as a preemptible machine, it cannot migrate to a regular VM. You could, however, save a snapshot and use that to create a new regular instance.

16. Custom VMs can have up to how many vCPUs? - C. 64

- C. Custom VMs can have up to 64 CPUs and up to 6.5GB of memory per vCPU.

17. When using the App Engine standard environment, which of the following language's runtime is not supported? - C. C

- C. The C programming language is not supported in the App Engine standard environment. If you need to run a C application, it can be compiled and run in a container running in the App Engine flexible environment.

18. Kubernetes reserves CPU resources in percentages of cores available. The percentage is what range? - B. 0.25 percent to 6 percent

- B. Kubernetes reserves CPU capacity according to the following schedule: 6 percent of the first core, 1 percent of the next core (up to two cores), 0.5 percent of the next two cores (up to four cores), 0.25 percent of any cores above four cores

19. Kubernetes deployments can be in what states? - B. Progressing, completed, failed

- B. The only states a Kubernetes deployment can be in are progressing, completed, and failed.

20. A client has brought you in to help reduce their DevOps overhead. Engineers are spending too much time patching servers and optimizing server utilization. They want to move to serverless platforms as much as possible. Your client has heard of Cloud Functions and wants to use them as much as possible. You recommend all of the following types of applications except which one? - A. Long-running data warehouse data load procedures

- A. Cloud Functions is best suited for event-driven processing, such as a file being uploaded to Cloud Storage or an event being written to a Pub/Sub queue. Long-running jobs, such as loading data into a data warehouse, are better suited to Compute Engine or App Engine.

### 5 Computing with Compute Engine Virtual Machines

Creating and Configuring Virtual Machines with the Console

Main Virtual Machine Configuration Details

"If you want the processes running on this VM to use only some APIs, you can use these options to limit the VM's access to specific APIs."

Additional Configuration Details

Management Tab

"Labels are particularly important when your number of servers grows."

"The Availability Policy sets three parameters."

"Shielded VMs are configured to have additional security mechanisms that you can choose to run."

"Secure Boot, which ensures that only authenticated operating system software runs on the VM."

"A TPM is a specialized computer chip designed to protect security resources, like keys and certificates."

"Integrity Monitoring, which uses a known good baseline of boot measurements to compare to recent boot measurements."

"GCP supports the concept of project-wide SSH keys, which are used to give users project-wide access to VMs."

"Using an existing disk in read-only mode is a good way of replicating reference data across multiple instances of VMs."

"If you need to ensure that your VMs run on a server only with your other VMs, then you can specify sole tenancy."

Creating and Configuring Virtual Machines with Cloud SDK

Installing Cloud SDK

Installing Cloud SDK on Linux

Cloud SDK on Mac OS

Installing Cloud SDK on Windows

Example Installation on Ubuntu Linux

Creating a Virtual Machine with Cloud SDK

"The `gcloud` command is organized into a hierarchy of groups, such as the compute group for Compute Engine commands."

"A subgroup is used in Compute Engine commands to indicate what type of compute resource you are working with."

"If you do not specify additional parameters, such as a zone, Google Cloud will use your information from your default project."

"To create a standard VM with 8 CPUs and 30GB of memory, you can specify n1-standard-8 as the machine type."

Creating a Virtual Machine with Cloud Shell

Basic Virtual Machine Management

Starting and Stopping Instances

Network Access to Virtual Machines

"As a cloud engineer, you will sometimes need to log into a VM to perform some administration tasks."

"The most common way is to use SSH when logging into a Linux server or Remote Desktop Protocol (RDP) when logging into a Windows server."

Monitoring a Virtual Machine

Cost of Virtual Machines

"If you want to track costs automatically, you can enable Cloud Platform billing and setup Billing Export."

"This will produce daily reports on the usage and cost of VMs."

"VMs are charged for a minimum of 1 minute of use."

Guidelines for Planning, Deploying, and Managing Virtual Machines

"Use the console for ad hoc administration of VMs."

"Use scripts with gcloud commands for tasks that will be repeated."

Summary

"When creating a VM, you have to specify a number of parameters, including a name for the VM, a region and zone where the VM will run, a machine type that specifies the number of vCPUs and the amount of memory, and a boot disk that includes an operating system."

"Common tasks when managing VMs are starting and stopping instances, using SSH to access a terminal on the VM, monitoring, and tracking the cost of the VM."

Exam Essentials

"Understand how to use Cloud Console and Cloud SDK to create, start, and stop VMs."

"Know how to configure a preemptible VM using Cloud Console and the `gcloud` commands."

"Know the purpose of advanced options, including Shielded VMs and advanced boot disk configurations."

"Know how to use `gcloud` compute instance commands to list, start, and stop VMs."

"Understand how to monitor a VM."

"Know the factors that determine the cost of a VM."

Review Questions

1. You have just opened the GCP console at `console.google.com`. You have authenticated with the user you want to use. What is one of the first things you should do before performing tasks on VMs? - C. Verify that the selected project is the one you want to work with.

- C. You should verify the project selected because all operations you perform will apply to resources in the selected project, making option C the correct answer. You do not need to open Cloud Shell unless you want to work with the command line, and if you did, you should verify that the project is correctly selected first. Logging into a VM using SSH is one of the tasks that requires you to be working with the correct project, so logging in via SSH should not happen before verifying the project. The list of VMs in the VM Instance window is a list of VMs in the current project. You should verify which project you are using to ensure you are viewing the set of VMs you think you are using.

2. What is a one-time tasks you will need to complete before using the console? - A. Set up billing

- A. You will need to set up billing if it is not already enabled when you start using the console, so option A is the right answer. You may create a project, but you will be able to do this only if billing is enabled. You do not need to create a storage bucket to work with the console. Specifying a default zone is not a one-time task; you may change zones throughout the life of your project.

3. A colleague has asked for your assistance setting up a test environment in Google Cloud. They have never worked in GCP. You suggest starting with a single VM. Which of the following is the minimal set of information you will need? - B. A name for the VM, a machine type, a region, and a zone

- B. The name of the VM, the region and zone, and the machine type can all be specified in the console along with other parameters, so option B is correct. Option A is missing required parameters. A CIDR block is a range of IP addresses that is associated with a subnet and not needed to create a VM. An IP address is assigned automatically so it is not required.

4. An architect has suggested a particular machine type for your workload. You are in the console creating a VM and you don't see the machine type in the list of available machine types. What could be the reason for this? - B. That machine type is not available in the zone you specified.

- B. Different zones may have different machine types available, so you will need to specify a region first and then a zone to determine the set of machine types available. If the machine type does not appear in the list, it is not available in that zone. This makes option B the correct answer. Options A and C are incorrect. Subnets and IP addresses are not related to the machine types available. Unless you are specifying a custom machine type, you do not specify the amount of memory; that is defined by the machine type, so option D is incorrect.

5. Your manager asks for your help with understanding cloud computing costs. Your team runs dozens of VMs for three different applications. Two of the applications are for use by the marketing department and one is used by the finance department. Your manager wants a way to bill each department for the cost of the VMs used for their applications. What would you suggest to help solve this problem? - C. Labels and descriptions

- C. Labels and descriptions are for helping us track our own attributes of resources; GCP does not need them to perform its tasks. As the number of servers grows, it can become difficult to track which VMs are used for which applications and services, so option C is the correct answer. Labels and a general description will help administrators track numbers of VMs and their related costs. Options A and B are used for security and storage but do not help with managing multiple VMs. Option D is only partly correct. Descriptions are helpful but so are labels.

6. If you wanted to set the preemptible property using Cloud Console, in which section of the Create An Instance page would you find the option? - A. Availability Policy

- A. The Availability Policy section within the Management tab is where you set preemptibility, so option A is correct. Identity And API Access is used to control the VM's access to Google Cloud APIs and which service account is used with the VM. Sole Tenancy is used if you need to run your VMs on physical servers that only run your VMs. Networking is used to set network tags and change the network interface.

7. You need to set up a server with a high level of security. You want to be prepared in case of attacks on your server by someone trying to inject a rootkit (a kind of malware that can alter the operating system). Which option should you select when creating a VM? - B. Shield VM

- B. Shield VM is an advanced set of security controls that includes Integrity Monitoring, a check to ensure boot images have not been tampered with, which makes option B the right answer. Firewalls are used to control ingress and egress of network traffic to a server or subnet. Project-wide SSH keys are used for authenticating users across servers within a project. Boot disk integrity check is a fictional feature.

8. All of the following parameters can be set when adding an additional disk through Google Cloud Console, except one. Which one? - C. Block size

- C. Block size is not an option in the Additional Disks dialog, so option C is correct. Encryption key management, disk type, and the option of specifying a source image are all available options.

9. You lead a team of cloud engineers who maintain cloud resources for several departments in your company. You've noticed a problem with configuration drift. Some machine configurations are no longer in the same state as they were when created. You can't find notes or documentation on how the changes were made or why. What practice would you implement to solve this problem? - B. Write scripts using gcloud commands to change configuration and store those scripts in a version control system.

- B. Using version-controlled scripts is the best approach of the four options. Scripts can be documented with reasons for the changes and they can be run repeatedly on different machines to implement the same change. This reduces the chance of error when manually entering a command. Option A does not help to improve documenting why changes were made. Option C could help improve documentation, but executable scripts are precise and accurate reflections of what was executed. Notes may miss details. Option D is not advisable. You could become a bottleneck to making changes, changes cannot be made when you are unavailable, and your memory may not be a reliable way to track all configuration changes.

10. When using the Cloud SDK command-line interface, which of the following is part of commands for administering resources in Compute Engine? - A. `gcloud compute instances`

- A. `gcloud compute instances` is the start of commands for administering Compute Engine resources, making option A the right answer. Option B, `gcloud instances`, is missing the compute keyword that indicates we are working with Compute Engine. Option C has switched the order of `compute` and `instances`. Option D is false because option A is the correct answer.

11. A newly hired cloud engineer is trying to understand what VMs are running in a particular project. How could the engineer get summary information on each VM running in a project? - B. Execute the command `gcloud compute instances list`

- B. Option B follows the pattern of the `gcloud` command, which is hierarchical and starts with the `gcloud` name of the service, in this case `compute` for Compute Engine, followed by the next level down, which in this case is `instances`. Finally, there is the action or verb, in this case `list`. Option A is missing the term `instances` to indicate you are working with VM instances. Option C is missing the `compute` keyword to indicate you are working with Compute Engine. Option D is missing the `compute instance` keyword and has switched the order of `instances` and `list`.

12. When creating a VM using the command line, how should you specify labels for the VM? - B. Use the `--labels` option with labels in the format of KEYS=VALUE.

- B. The correct format is to use the `--labels` parameter and specify the key followed by an equal sign followed by the value in option B. Options A and C have the wrong character separating the key and value. Option D is incorrect because it is possible to specify labels in the command line.

13. In the boot disk advanced configuration, which operations can you specify when creating a new VM? - C. Add a new disk and attach an existing disk

- C. The two operations you can specify when using the boot disk configuration are adding a new disk and attaching an existing disk, so option C is correct. Reformatting an existing disk is not an option, so options A, B, and D cannot be the correct answer.

14. You have acquired a 10 GB data set from a third-party research firm. A group of data scientists would like to access this data from their statistics programs written in R. R works well with Linux and Windows file systems, and the data scientists are familiar with file operations in R. The data scientists would each like to have their own dedicated VM with the data available in the VM's file system. What is a way to make this data readily available on a VM and minimize the steps the data scientists will have to take? - B. Create VMs using a source image created from a disk with the data on it.

- B. 10 GB of data is small enough to store on a single disk. By creating an image of a disk with the data stored on it, you can specify that source image when creating a VM. Option A would require the data scientist to copy the data from Cloud Storage to a disk on the VM. Option C would similarly require copying the data. Option D would load data into a database, not a file system as specified in the requirements.

15. The Network tab of the create VM form is where you would perform which of the following operations? - B. Add a network interface to the VM

- B. In the Network tab of the VM form, you can add another network interface, so option B is correct. GCP sets the IP address, so option A is incorrect. There is no option to specify a router or change firewall rules on the network tab, so options C and D are incorrect.

16. You want to create a VM using the `gcloud` command. What parameter would you include to specify the type of boot disk? - A. `boot-disk-type`

- A. The correct option is `boot-disk-type`, which is option A. The other three options are not parameters to the `gcloud compute instances` command.

17. Which of the following commands will create a VM with four CPUs that is named web-server-1? - A. `gcloud compute instances create --machine-type=n1-standard-4 web-server-1`

- A. Option A is the correct command. It is the only option that includes a correct machine type and properly specifies the name of the instance. Option B uses the `--cpus` parameter, which does not exist. Option C uses the parameter `instance-name`, which does not exist. The instance name is passed as an argument and does not need a parameter name. Option D is incorrect because `machine type n1-4-cpu` is not a valid machine type.

18. Which of the following commands will stop a VM named web-server-1? - C. `gcloud compute instances stop web-server-1`

- C. Option C is the correct command, which is `gcloud compute instances`, to indicate you are working with VMs, followed by the `stop` command and the name of the VM. Option A is incorrect because `halt` is not an option. Option B is incorrect because `-terminate` is not a parameter. Option D is missing the word `instances`, which indicates you are working with VMs.

19. You have just created an Ubuntu VM and want to log into the VM to install some software packages. Which network service would you use to access the VM? - B. SSH

- B. SSH is a service for connecting to a remote server and logging into a terminal window. Once logged in, you would have access to a command line, so option B is the right answer. FTP is a file transfer protocol and does not allow you to log in and perform system administration tasks. RDP is a protocol used to remotely access Windows servers, not Ubuntu, which is a Linux distribution. `ipconfig` is a command-line utility for configuring IP stacks on a device and does not allow you to log into a remote server.

20. Your management team is considering three different cloud providers. You have been asked to summarize billing and cost information to help the management team compare cost structures between clouds. Which of the following would you mention about the cost of VMs in GCP? - A. VMs are billed in 1-second increments, cost varies with the number of CPUs and amount of memory in a machine type, you can create custom machine types, preemptible VMs cost up to 80 percent less than standard VMs, and Google offers discounts for sustained usage.

- A. All of the statements in option A are true and relevant to billing and costs. Option B is correct that VMs are billed in 1-second increments, but the only preemptible VMs are shut down within 24 hours of starting. Option C is incorrect because discounts are not limited to some regions. Option D is incorrect because VMs are not charged for a minimum of 1 hour.

### 6 Managing Virtual Machines

"After creating virtual machines, a cloud engineer will need to work with both single instances of virtual machines (VMs) and groups of VMs that run the same configuration."

"The latter are called instance groups and are introduced in this chapter."

Managing Single Virtual Machine Instances

Managing Single Virtual Machine Instances in the Console

Starting, Stopping, and Deleting Instances

Viewing Virtual Machine Inventory

Attaching GPUs to an Instance

"Also, if you add a GPU to a VM, you must set the instance to terminate during maintenance. This is set in the Availability Policies section of the VM configuration form."

Working with Snapshots

"Snapshots are copies of data on a persistent disk."

"When you first create a snapshot, GCP will make a full copy of the data on the persistent disk."

"If you are running a database or other application that may buffer data in memory before writing to disk, be sure to flush disk buffers before you create the snapshot; otherwise, data in memory that should be written to disk may be lost."

"To work with snapshots, a user must be assigned the Compute Storage Admin role."

Working with Images

Managing a Single Virtual Machine Instance with Cloud Shell and the Command Line

Starting Instances

Stopping Instances

Deleting Instances

Viewing VM Inventory

Working with Snapshots

Working with Images

"The `source-disk`, `source-image`, and `source-snapshot` parameters are used to create an image using a disk, image, and snapshot, respectively."

"Families are groups of related images, which are usually different versions of the same underlying image."

Introduction to Instance Groups

Creating and Removing Instance Groups and Templates

"To create an instance group, you must first create an instance group template."

"Instance groups can contain instances in a single zone or across a region."

"Regional managed instance groups are recommended because that configuration spreads the workload across zones, increasing resiliency."

Instance Groups Load Balancing and Autoscaling

"You can configure an autoscaling policy to trigger adding or removing instances based on CPU utilization, monitoring metric, load-balancing capacity, or queue-based workloads."

Guidelines for Managing Virtual Machines

"Use labels and descriptions."

"Use manage instance groups to enable autoscaling and load balancing."

"Use GPUs for numeric-intensive processing, such as machine learning and high-performance computing."

"Use snapshots to save the state of a disk or to make copies."

"Use preemptible instances for workloads that can tolerate disruption."

Summary

Exam Essentials

"Understand how to navigate Cloud Console."

"Understand how to install Cloud SDK."

"Know how to create a VM in the console and at the command line."

"Understand why GPUs are used and how to attach them to a VM."

"Understand images and snapshots."

"Understand instance groups and instance group templates."

Review Questions

1. Which page in Google Cloud Console would you use to create a single instance of a VM? - A. Compute Engine

- A. The Compute Engine page is where you have the option of creating a single VM instance, so option A is the correct answer. App Engine is used for containers and running applications in language-specific runtime environments. Kubernetes Engine is used to create and manage Kubernetes clusters. Cloud Functions is where you would create a function to run in Google's serverless cloud function environment.

2. You view a list of Linux VM instances in the console. All have public IP addresses assigned. You notice that the SSH option is disabled for one of the instances. Why might that be the case? - B. The instance is stopped.

- B. Instances can be stopped, and when they are, then you cannot connect to them via SSH, which makes option B the correct answer. Starting the instance will enable SSH access. Option A is not correct because you can log into preemptible machines. Option C is incorrect because there is no No SSH option. Option D is incorrect because the SSH option can be disabled.

3. You have noticed unusually slow response time when issuing commands to a Linux server, and you decide to reboot the machine. Which command would you use in the console to reboot? - B. Reset

- B. The Reset command can be used to restart a VM; thus, option B is correct. The properties of the VM will not change, but data in memory will be lost. There is no Reboot, Restart, Shutdown, or Startup option in the console.

4. In the console, you can filter the list of VM instances by which of the following? - C. Labels, status, or members of managed instance group

- C. Labels, members of a managed instance group, and status are all available for filtering, so option C is the correct answer. You can also filter by internal IP, external IP, zone, network, deletion protection, and member of a managed or unmanaged instance group.

5. You will be building a number of machine learning models on an instance  and attaching GPU to the instance. When you run your machine learning models they take an unusually long time to run. It appears that GPU is not being used. What could be the cause of this? - A. GPU libraries are not installed.

- A. To function properly, the operating system must have GPU libraries installed, so option A is correct. The operating system does not have to be Ubuntu based, and there is no need to have at least eight CPUs in an instance before you can attach and use a GPU. Available disk space does not determine if a GPU if used or not.

6. When you add a GPU to an instance, you must ensure that: - A. The instance is set to terminate during maintenance.

- A. If you add a GPU to a VM, you must set the instance to terminate during maintenance, which makes option A the correct response. This is set in the Availability Policies section of the VM configuration form. The instance does not need to be preemptible and it can have non-boot disks attached. The instance is not required to run Ubuntu 14.02 or later.

7. You are using snapshots to save copies of a 100GB disk. You make a snapshot and then add 10GB of data. You create a second snapshot. How much storage is used in total for the two snapshots (assume no compression)? - B. 110 GB, with 100GB for the first and 10GB for the second.

- B. When you first create a snapshot, GCP will make a full copy of the data on the persistent disk. The next time you create a snapshot from that disk, GCP does not store a full copy of the second snapshot. Option C is incorrect; the first snapshot is not deleted automatically. Option D is incorrect, subsequent snapshots do not incur 10 percent overhead.

8. You have decided to delegate the task of making backup snapshots to a member of your team. What role would you need to grant to your team member to create snapshots?

- D. To work with snapshots, a user must be assigned the Compute Storage Admin role, which makes option D the correct answer. The other options are fictitious roles.

9. The source of an image may be: - C. Disks, snapshots, or another image

- C. Images can be created from four sources, namely, disks, snapshots, cloud storage files, or another image, so option C is the right answer. Database export files are not sources for images.

10. You have built images using Ubuntu 14.04 and now want users to start using Ubuntu 16.04. You don't want to just delete images based on Ubuntu 14.04, but you want users to know they should start using Ubuntu 16.04. What features of images would you use to accomplish this? - B. Deprecated

- B. Deprecated marks the image as no longer supported and allows you to specify a replacement image to use going forward, making option B the correct answer. Deprecated images are available for use but may not be patched for security flaws or have other updates. The other options are fictitious features of images.

11. You want to generate a list of VMs in your inventory and have the results in JSON format. What command would you use? - C. `gcloud compute instances list --format json`

- C. The base command for working with instances is `gcloud compute instances`, which makes option C the correct answer. The `list` command is used to show details of all instances. By default, `output` is in human-readable form, not `json`. Using the `--format json` option forces the output to be in JSON format. `--output` is not a valid option.

12. You would like to understand details of how GCP starts a virtual instance. Which optional parameter would you use when starting an instance to display those details?

- B. `--async` causes information about the start process to be displayed; therefore option B is correct. `--verbose` is an analogous parameter in many Linux commands. `--describe` provides details about an instance but not necessarily the startup process. `--details` is not a valid parameter.

13. Which command will delete an instance named ch06-instance-3? - C. `gcloud compute instances delete ch06-instance-3`

- C. The command to delete an instance is `gcloud compute instances delete` followed by the name of the instance, so option C is correct. Option A is incorrect because there is no `instance` parameter. Option B is incorrect because that command stops but does not delete the instance. Option D is missing `instances` in the command, which is required to indicate what type of entity is being deleted.

14. You are about to delete an instance named ch06-instance-1 but want to keep its boot disk. You do not want to keep other attached disks. What `gcloud` command would you use? - A. `gcloud compute instances delete ch06-instance-1 --keep-disks=boot`

- A. `gcloud compute instances` is the base command followed by `delete`, the name of the instance, and `--keep-disks=boot`, so option A is correct. There is no `--save-disk` parameter. Option C is wrong because `filesystem` is not a valid value for the `keep-disk` parameter. Option D is missing the `instances` option which is required in the command.

15. You want to view a list of fields you can use to sort a list of instances. What command would you use to see the field names?

- B. The correct answer is option B, which is to use the `describe` command. Option A will show some fields but not all. Options C and D are incorrect because there is no `detailed` parameter.

16. You are deploying an application that will need to scale and be highly available. Which of these Compute Engine components will help achieve scalability and high availability? - B. Instance groups

- B. Instance groups are sets of VMs that can be configured to scale and are used with load balancers, which contribute to improving availability, so option B is correct. Preemptible instances are not highly available because they can be shut down at any time by GCP. Cloud Storage is not a Compute Engine component. GPUs can help improve throughput for math-intensive operations but do not contribute to high availability.

17. Before creating an instance group, you need to create what? - B. Instance group template

- B. An instance group template is used to specify how the instance group should be created, which makes option B the correct answer. Option A is incorrect because instances are created automatically when an instance group is created. Boot disk images and snapshots do not have to be created before creating an instance group.

18. How would you delete an instance group template using the command line? - B. `gcloud compute instance-templates delete`

- B. The command to delete an instance group is `gcloud compute instance-template-delete`, so option B is correct. Option A incorrectly includes the term `instances`. Option C is in incorrect order. Option D is wrong because `instance-template` is in the wrong position and is plural in the option.

19. What can be the basis for scaling up an instance group? - C. Network latency, load balancing capacity, and CPU utilization

- C. You can configure an autoscaling policy to trigger adding or removing instances based on CPU utilization, monitoring metric, load balancing capacity, or queue-based workloads. Disk, network latency, and memory can trigger scaling if monitoring metrics on those resources are configured. So, option C is correct.

20. An architect is moving a legacy application to Google Cloud and wants to minimize the changes to the existing architecture while administering the cluster as a single entity. The legacy application runs on a load-balanced cluster that runs nodes with two different configurations. The two configurations are required because of design decisions made several years ago. The load on the application is fairly consistent, so there is rarely a need to scale up or down. What GCP Compute Engine resource would you recommend using? - B. Unmanaged instance groups

- B. Unmanaged instance groups are available for limited use cases such as this. Unmanaged instance groups are not recommended in general. Managed instance groups are the recommended way to use instance groups, but the two different configurations prevents their use. Preemptible instances and GPUs are not relevant to this scenario.

### 7 Computing with Kubernetes

Introduction to Kubernetes Engine

"Kubernetes runs containers on a cluster of virtual machines (VMs)."

"It determines where to run containers, monitors the health of containers, and manages the full lifecycle of VM instances."

"This collection of tasks is known as container orchestration."

"Instance groups, however, are much more restricted."

"All VMs generally run the same image in an instance group."

"Also, instance groups have no mechanism to support the deployment of containers."

"Containers offer a highly-portable, light-weight means of distributing and scaling your applications or workloads, like VMs, without replicating the guest OS."

"They can start and stop much faster (usually in seconds) and use fewer resources."

"Instance groups have some monitoring and can restart instances that fail, but Kubernetes has much more flexibility with regard to maintaining a cluster of servers."

Kubernetes Cluster Architecture

"A Kubernetes cluster consists of a cluster master and one or more nodes, which are the workers of the cluster."

"The cluster master manages services provided by Kubernetes, such as the Kubernetes API, controllers, and schedulers."

"Users can also interact with a cluster using the `kubectl` command.

"The nodes run an agent called kubelet, which is the service that communicates with the cluster master."

Kubernetes Objects

Pods

"Pods are single instances of a running process in a cluster."

"Pods contain at least one container."

"They usually run a single container, but can run multiple containers."

"Multiple containers are used when two or more containers must share resources."

"Pods also use shared networking and storage across containers."

"Each pod gets a unique IP address and a set of ports."

"Multiple containers in a pod connect to different ports and can talk to each other on localhost."

"This structure is designed to support running one instance of an application within the cluster as a pod."

"A pod allows its containers to behave as if they are running on an isolated VM, sharing common storage, one IP address, and a set of ports."

"By doing this, you can deploy multiple instances of the same application, or different instances of different applications on the the same node or different nodes, without having to change their configuration."

"Pods treat the multiple containers as a single entity for management purposes."

"Pods are generally created in groups."

"Replicas are copies of pods and constitute a group of pods that are managed as a unit."

"Pods are considered ephemeral; that is, they are expected to terminate."

"If a pod is unhealthy – for example, if it is stuck in a waiting mode or crashing repeatedly – it is terminated."

"The mechanism that manages scaling and health monitoring is known as a controller."

"A key difference is that pods are for executing applications in containers and may be placed on various nodes in the cluster, while managed instance groups all execute the same application code on each of the nodes."

"Also, you typically manage instance groups yourself by executing commands in Cloud Console or through the command line."

"Pods are usually managed by a controller."

Services

"Since pods are ephemeral and can be terminated by a controller, other services that depend on pods should not be tightly coupled to particular pods."

"For example, even though pods have unique IP addresses, applications should not depend on that IP address to reach an application."

"Kubernetes provides a level of indirection between applications running in pods other applications that call them: it is called a service."

"A service, in Kubernetes terminology, is an object that provides API endpoints with a stable IP address that allow applications to discover pods running a particular application."

"Services update when changes are made to pods, so they maintain an up-to-date list of pods running an application."

ReplicaSet

"A ReplicaSet is a controller used by a deployment that ensures the correct number of identical pods are running."

"For example, if a pod is determined to be unhealthy, a controller will terminate that pod."

"The ReplicaSet will detect that not enough pods for that application or workload are running and will create another."

Deployment

"Deployments are sets of identical pods."

"The members of the set may change as some pods are terminated and others are started, but they are all running the same application."

"The pods all run the same application because they are created using the same pod template."

"A pod template is a definition of how to run a pod."

"The description of how to define the pod is called a pod specification."

"That is, if the specification has a minimum number of pods that should be in the deployment and the number falls below that, then additional pods will be added to the deployment by calling on a ReplicaSet."

StatefulSet

"Deployments are well suited to stateless applications."

"StatefulSets are used when an application needs a unique network identifier or stable persistent storage."

Job

"A job is an abstraction about a workload."

"Jobs create pods and run them until the application completes a workload."

"Job specifications are specified in a configuration file and include specifications about the container to use and what command to run."

Deploying Kubernetes Clusters

Deploying Kubernetes Clusters Using Cloud Console

"The first time you use Kubernetes Engine, you may need to create credentials."

"For example, if you want to run VMs in different zones to improve availability, you can specify multiple node pools."

"They're much like a Managed Instance Group but not the same."

Deploying Kubernetes Clusters Using Cloud Shell and Cloud SDK

Deploying Application Pods

"Once you have specified a deployment, you can display the corresponding YAML specification, which can be saved and used to create deployments from the command line."

Monitoring Kubernetes

"Stackdriver supports more advanced alerting as well, including process health, uptime checks, group aggregate thresholds, and metric rates of change."

Summary

"Kubernetes Engine is a container orchestration system for deploying applications to run in clusters."

"Kubernetes is architected with a single cluster manager and worker nodes."

"Kubernetes uses the concept that pods are instances running a container."

"It is possible to run multiple containers in a pod, but that occurs less frequently than single-container pods."

"ReplicaSets are controllers for ensuring that the correct number of pods are running."

"Deployments are sets of identical pods."

"StatefulSets are a type of deployment used for stateful applications."

"You deploy applications by bundling the application in a container and using the console or the `kubectl` command to create a deployment that runs the application on the cluster."

Exam Essentials

"Understand that Kubernetes is a container orchestration system."

"Understand that Kubernetes uses a single cluster master that controls nodes that executes workloads."

"Be able to describe pods."

"Kubernetes can be deployed using Cloud Console or using `gcloud` commands."

"Deployments are sets of identical pods."

"StatefulSets are a type of deployment used for stateful applications."

"Kubernetes is monitored using Stackdriver."

Review Questions

1. A new engineer is asking for clarification about when it is best to use Kubernetes and when to use instance groups. You point out that Kubernetes uses instance groups. What purpose do instance groups play in a Kubernetes cluster? - C. They create sets of VMs that can be managed as a unit.

- C. Kubernetes creates instance groups as part of the process of creating a cluster, which makes option C the correct answer. Stackdriver, not instance groups, is used to monitor the health of nodes and to create alerts and notifications. Kubernetes creates pods and deployments; they are not provided by instance groups.

2. What kinds of instances are required to have a Kubernetes cluster? - A. A cluster master and nodes to execute workloads.

- A. A Kubernetes cluster has a single cluster master and one or more nodes to execute workloads, so option A is the correct answer. Stackdriver is not part of the Kubernetes cluster; it is a separate GCP service. Kubernetes does not require instances with at least four vCPUs; in fact, the default node configuration uses one vCPU.

3. What is a pod in Kubernetes? - C. A single instance of a running process in a cluster

- C. Pods are single instances of a running process in a cluster, so option C is correct. Pods run containers but are not sets of containers. Application code runs in containers that are deployed in pods. Pods are not controllers, so they cannot manage communication with clients and Kubernetes services.

4. You have developed an application that calls a service running in a Kubernetes cluster. The service runs in pods that can be terminated if they are unhealthy and replaced with other pods that might have a different IP address. How should you code your application to ensure it functions properly in this situation? - B. Communicate with Kubernetes services so applications do not have to be coupled to specific pods.

- B. Services are applications that provide API endpoints that allow applications to discover pods running a particular application, making option B correct. Options A and C, if they could be coded using the API designed for managing clusters, would require more code than working with services and are subject to changes in a larger set of API functions. Option D is not an actual option.

5. You have noticed that an application's performance has degraded significantly. You have recently made some configuration changes to resources in your Kubernetes cluster and suspect that those changes have alerted the number of pods running in the cluster. Where would you look for details on the number of pods that should be running? - C. ReplicaSet

- C. ReplicaSets are controllers that are responsible for maintaining the correct number of pods, which makes option C the correct answer. Deployments are versions of application code running on a cluster. Stackdriver is a monitoring and logging service that monitors but does not control Kubernetes clusters. Jobs is an abstraction of workloads and is not tied to the number of pods running in a cluster.

6. You are deploying a high availability application in Kubernetes Engine. You want to maintain availability even if there is a major network outage in a data center. What feature of Kubernetes Engine would you employ? - B. Multizone/region cluster

- B. Multizone/multiregion clusters are available in Kubernetes Engine and are used to provide resiliency to an application, so option B is correct. Option A refers to instance groups that are a feature of Compute Engine, not directly of Kubernetes Engine. Option C is incorrect; regional deployments is a fictitious term. Load balancing distributes load and is part of Kubernetes by default. If load is not distributed across zones or regions, it does not help to add resiliency across data centers.

7. You want to write a script to deploy a Kubernetes cluster with GPUs. You have deployed clusters before, but you are not sure about all the required parameters. You need to deploy this script as quickly as possible. What is one way to develop this script quickly? - A. Use the GPU template in the Kubernetes Engine cloud console to generate the `gcloud` command to create the cluster

- A. Option A is the best answer. Starting with an existing template, filling in parameters, and generating the `gcloud` command is the most reliable way. Option D may work, but multiple parameters that are needed for your configuration may not be in the script you start with. There may be some trial and error with this option. Options B and C may lead to a solution but could take some time to complete.

8. What `gcloud` command will create a cluster named ch07-cluster-1 with four nodes? - C. `gcloud container clusters create ch07-cluster-1 --num-nodes=4`

- C. The correct command is option A [not anymore!]. Option B has `beta` in the wrong position. Option C is missing `beta`. Option D is missing the `--num-nodes` parameter name.

9. When using Create Deployment from Cloud Console, which of the following cannot be specified for a deployment? - C. Time to live (TTL)

- C. Time to Live is not an attribute of deployments, so option C is the correct answer. Application name, container image, and initial command can all be specified.

10. Deployment configuration files created in Cloud Console use what type of file format? - B. YAML

- B. Deployment configuration files created in Cloud Console are saved in YAML format. CSV, TSV, and JSON are not used.

11. What command is used to run a Docker image on a cluster? - C. `kubectl run`

- C. The `kubectl` command is used to control workloads on a Kubernetes cluster once it is created, so option C is correct. Options A and B are incorrect because `gcloud` is not used to manipulate Kubernetes processes. Option D is wrong because `beta` is not required in `kubectl` commands.

12. What command would you use to have 10 replicas of a deployment named ch07-app-deploy? - C. `kubectl scale deployment ch07-app-deploy --replicas=10`

- C. Option C is the correct command. Option A uses the term `upgrade` instead of `scale`. Option B incorrectly uses `gcloud`. Option D uses the incorrect parameter pods.

13. Stackdriver is used for what operations on Kubernetes clusters? - D. Notifications, monitoring, and logging

- D. Stackdriver is a comprehensive monitoring, logging, alerting, and notification service that can be used to monitor Kubernetes clusters.

14. Before monitoring a Kubernetes cluster, what must you create with Stackdriver? - B. Workspace

- B. Workspaces are logical structures for storing information about resources in a project that are being monitored, so option B is correct. Stackdriver works with logs, but a log is not required before starting to use Stackdriver. Pods and ReplicaSets are part of Kubernetes, not Stackdriver.

15. What kind of information is provided in the Details page about an instance in Stackdriver? - C. Disk I/O, CPU usage, and network traffic

- C. The Stackdriver Instance Detail page includes time-series charts on CPU usage, network traffic, and disk I/O.

16. When creating an alerting policy, what can be specified? - B. Conditions, notifications, and documentation

- B. When creating an alert policy, you can specify conditions, notifications, and documentation, making option B the correct answer. Options A and D are incorrect because there is no Time to Live attribute on policies. Option C is wrong because it does not include notifications and documentation.

17. Your development team needs to be notified if there is a problem with applications running on several Kubernetes clusters. Different team members prefer different notification methods in addition to Stackdriver alerting. What is the most efficient way to send notifications and meet your team's requests? - A. Set up SMS text messaging, Slack, and email notifications on an alert.

- A. Alerts can have multiple channels, so Option A is correct. Channels include email, webhooks, and SMS text messaging as well as third-party tools such as PagerDuty, Campfire, and Slack. There is no need for multiple alerts with individual notifications. Option C is ad hoc and would require additional maintenance overhead. Option D does not meet requirements.

18. A new engineer is trying to set up alerts for a Kubernetes cluster. The engineer seems to be creating a large number of alerts and you are concerned this is not the most efficient way and will lead to more maintenance work than required. You explain that a more efficient way is to create alerts and apply them to what? - B. An instance or entire group

- B. Alerts are assigned to instances or sets of instances; therefore, option B is correct. Option A is incorrect because it does not include groups. Option C is incorrect because it does not include instances. Option D is wrong because alerts are not assigned to pods.

19. You are attempting to execute commands to initiate a deployment on a Kubernetes cluster. The commands are not having any effect. You suspect that a Kubernetes component is not functioning correctly. What component could be the problem? - 

- A. All interactions with the cluster are done through the master using the Kubernetes API. If an action is to be taken on a node, the command is issues by the cluster master, so option A is the correct answer. Options B and D are incorrect because they are controllers within the cluster and do not impact how commands are received from client devices. Option C is incorrect because `kubectl`, not `gcloud`, is used to initiate deployments.

20. You have deployed an application to a Kubernetes cluster. You have noticed that several pods are starved for resources for a period of time and the pods are shut down. When resources are available, new instantiations of those pods are created. Client are still able to connect to pods even though thee new pods have different IP addresses from the pods that were terminated. What Kubernetes component makes this possible? - A. Services

- A. Services provide a level of indirection to accessing pods. Pods are ephemeral. Clients connect to services, which can discover pods. ReplicaSets and StatefulSets provide managed pods. Alerts are for reporting on the state of resources.

### 8 Managing Kubernetes Clusters 

Viewing the Status of a Kubernetes Cluster

Viewing the Status of Kubernetes Clusters Using Cloud Console

Pinning Services to the Top of the Navigation Menu

"Other possible statuses are Pending, which indicates the pod is downloading images; Succeeded, which indicates the pod terminated successfully; Failed, which indicates at least one container failed; and Unknown, which means the master cannot reach the node and status cannot be determined.

Viewing the Status of Kubernetes Clusters Using Cloud SDK and Cloud Shell

"To list information about nodes and pods, use the `kubectl` command."

Adding, Modifying, and Removing Nodes

Adding, Modifying, and Removing Nodes with Cloud Console

"Once a cluster has been created, you can modify it using the `gcloud container clusters update` command."

Adding, Modifying, and Removing Pods

Adding, Modifying, and Removing Pods with Cloud Console

"A deployment includes a configuration parameter called replicas, which are the number of pods running the application specified in the deployment."

Adding, Modifying, and Removing Pods with Cloud SDK and Cloud Shell

"To have Kubernetes manage the number of pods based on load, use the `autoscale` command."

Adding, Modifying, and Removing Services

Adding, Modifying, and Removing Services with Cloud Console

Adding, Modifying, and Removing Services with Cloud SDK and Cloud Shell

Viewing the Image Repository and Image Details

Viewing the Image Repository and Image Details with Cloud Console

Viewing the Image Repository and Image Details with Cloud SDK and Cloud Shell

Summary

Exam Essentials

"Know how to view the status of a Kubernetes cluster."

"Understand how to add, modify, and remove nodes."

"Understand how to add, modify, and remove pods."

"Understand how to add, modify, and remove services."

"Know how to view Container Registry images and their details."

Review Questions

1. You are running several microservices in a Kubernetes cluster. You've noticed some performance degradation. After reviewing some logs, you begin to think the cluster may be improperly configured, and you open Cloud Console to investigate. How do you see the details of a specific cluster? - B. Click the cluster name.

- B. When on the Cloud Console pages, you can click the cluster name to see a details page, so option B is the correct answer. Typing the name of cluster in the search bar does not always return cluster details; it can return instance group details. There is no such command as `gcloud cluster details`.

2. You are viewing the details of a cluster in Cloud Console and want to see how many vCPUs are available in the cluster. Where would you look for that information? - D. A and C

- D. You can find the number of vCPUs on the cluster listing in the Total Cores column or on the Details page in the Node Pool section in the size parameter, making option D correct. The Labels section does not have vCPU information.

3. You have been assigned to help diagnose performance problems with applications running on several Kubernetes clusters. Which command should you use? - B. `gcloud containers clusters list`

- B. The correct command includes `gcloud container` to describe the service, `clusters` to indicate the resource you are referring to, and `list` to indicate the command, which makes option B the correct answer. Options A and C are not valid commands.

4. When you first try to use the `kubectl` command, you get an error message indicating that the resource cannot be found or you cannot connect to the cluster. What command would you use to try to eliminate the error? - B. `gcloud container clusters get-credentials`

- B. It is likely you do not have access privileges to the cluster. The `gcloud container clusters get-credentials` command is the correct command to configure `kubectl` to use GCP credentials for the cluster, so option B is the right option. Options A, C, and D are invalid commands.

5. An engineer recently joined your team and is not aware of your team's standards for creating clusters and other Kubernetes objects. In particular, the engineer has not properly labeled several clusters. You want to modify the labels on the cluster from Cloud Console. How would you do it? - C. Click the Edit menu option.

- C. Clicking the Edit button allows you to change, add, or remove labels, so option C is the correct answer. The Connect button is on the cluster listing page, and the Deploy button is for creating new deployments. There is no way to enter labels under the Labels section when displaying details.

6. You receive a page in the middle of the night informing you that several services running on a Kubernetes cluster have high latency when responding to API requests. You review monitoring data and determine that there are not enough resources in the cluster to keep up with the load. You decide to add six more VMs to the cluster. What parameters will you need to specify when you issue the `cluster resize` command? - D. All of the above

- D. When resizing, the `gcloud container clusters resize` command requires the name of the cluster and the node pool to modify. The size is required to specify how many nodes should be running. Therefore, option D is correct.

7. You want to modify the number of pods in a cluster. What is the best way to do that? - B. Modify deployments

- B. Pods are used to implement replicas of a deployment. It is a best practice to modify the deployments, which are configured with a specification of the number of replicas that should always run, so option B is the correct answer. Option A is incorrect; you should not modify pods directly. Options C and D are incorrect because they do not change the number of pods running an application.

8. You want to see a list of deployments. Which option from the Kubernetes Engine navigation menu would you select? - C. Workloads

- C. Deployments are listed under Workloads, making option C the correct answer. The Cluster option shows details about clusters but does not have details on deployments. Storage shows information about persistent volumes and storage classes. Deployments is not an option. 

9. What actions are available from the Actions menu when viewing deployment details? - B. Autoscale, Expose, and Rolling Update

- B. There are four actions available for deployments (Autoscale, Expose, Rolling Update, and Scale), so option B is correct. Add, Modify, and Delete are not options.

10. What is the command to list deployments from the command line? - C.  `kubectl get deployments`

- C. Since deployments are managed by Kubernetes and not GCP, we need to use a `kubectl` command and not a `gcloud` command, which makes option C correct. Option D is incorrect because it follows the `gcloud` command structure, not the `kubectl` command structure. The `kubectl` command has the verb, like `get`, before the resource type, like `deployments`, for example. 

11. What parameters of a deployment can be set in the Create Deployment page in Cloud Console? - D. All of the above

- D. You can specify container image, cluster name, and application name along with the labels, initial command, and namespace; therefore, option D is the correct answer.

12. Where can you view a list of services when using Cloud Console? - A. In the Deployment Details page

- A. The Deployment Details page includes services, so option A is the correct answer. Containers are used to implement services; service details are not available there. The Clusters Detail page does not contain information on services running in the cluster.

13. What `kubectl` command is used to add a service? - A. `run`

- A. `kubectl run` is the command used to start a deployment. It takes a name for the deployment, an image, and a port specification. The other options are not valid `kubectl` commands.

14. You are supporting machine learning engineers who are testing a series of classifiers. They have five classifiers, called ml-classifier-1, ml-classifier-2, etc. They have found that ml-classifier-3 is not functioning as expected and they would like it removed from the cluster. What would you do to delete a service called ml-classifier-3? - A. Run the command `kubectl delete service ml-classifier-3`

- A. Option A shows the correct command, which is `kubectl delete service ml-classifier-3`. Option B is missing the service term. Options C and D cannot be correct because services are managed by Kubernetes, not GCP. 

15. What service is responsible for managing container images? - C. Container Registry

- C. The Container Registry is the service for managing images that can be used in other services, including Kubernetes Engine and Compute Engine, making option C correct. Both Compute Engine and Kubernetes Engine use images but do not manage them. There is no service called Container Engine. 

16. What command is used to list container images in the command line? - A. `gcloud container images list`

- A. Images are managed by GCP, so the correct command will be a `gcloud` command, so option A is the correct answer. Option B is incorrect because the verb is placed before the resource. Options C and D are incorrect because `kubectl` is for managing Kubernetes resources, not GCP resources like container images.

17. A data warehouse designer wants to deploy an extraction, transformation, and load process to Kubernetes. The designer provided you with a list of libraries that should be installed, including drivers for GPUs. You have a number of container images that you think may meet the requirements. How could you get a detailed description of each of those containers? - B. Run the command `gcloud container images describe`

- B. The correct command is `gcloud container images describe`, which makes option B the right answer. `describe` is the `gcloud` verb or operation for showing the details of an object. All other options are invalid commands.

18. You have just created a deployment and want applications outside the cluster to have access to the services provided by the deployment. What do you need to do to the service? - B. Issue a `kubectl expose deployment` command.

- B. The `kubectl expose deployment` command makes a service accessible, so option B is the correct answer. IP addresses are assigned to VMs, not services. The command `gcloud` does not manage Kubernetes services, so option C is incorrect. Option D is incorrect because making a service accessible is not a cluster-level task.

19. You have deployed an application to a Kubernetes cluster that processes sensor data from a fleet of delivery vehicles. The volume of incoming data depends on the number of vehicles making deliveries. The number of vehicles making deliveries is dependent on the number of customer orders. Customer orders are high during daytime hours, holiday seasons, and when major advertising campaigns are run. You want to make sure you have enough nodes running to handle the load, but you want to keep your costs down. How should you configure your Kubernetes cluster? - B. Enable autoscaling.

- B. Autoscaling is the most cost-effective and least burdensome way to respond to changes in demand for a service, so option B is the correct answer. Option A may run nodes even when they are not needed. Option C is manually intensive and requires human intervention. Option D reduces human intervention but does not account for unexpected spikes or lulls in demand.

20. When using Kubernetes Engine, which of the following might a cloud engineer need to configure? - B. Nodes, pods, services, clusters, and container images

- B. Cloud engineers working with Kubernetes will need to be familiar with working with clusters, nodes, pods, and container images. They will also need to be familiar with deployment. Option B is the correct answer because the other options are all missing an important component of Kubernetes that cloud engineers will have to manage.

### 9 Computing with App Engine
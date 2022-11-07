# AWS Technology

[AWS Review Notes Table of Contents](https://github.com/pslucas0212/AWS-Review-Notes)

### AWS Services

#### Compute
- EC2 - Elastic Cloud Compute. EC2 allows you to rent and manage virtual servers in the cloud.  Provision with one click.  Chose pre-configured template from Amazon Machine Image (AMI). Configure and manages EC2 instance from the AWS Management console.  SSH secure connection to laptop.  EC2 Instance Connect (EIC) allows you to use IAM policies to control SSH access without the need to manage SSH keys.  Systems manages connects to EC2 via web browser or AWS CLI.
  - Pricing Options
    - On-demand - Live on-demand fixed billing down to the second
    - Spot
    - Reserved Instances - commit to a specific instance in a specific region
    - Dedicated Hosts
    - Savings plans - commit to a usage spend
  - Features
    - Elastic Load Balance across EC2 instances - classic load balancers   |   application load balancers   |   gateway load balancers   |   network load balancers
    - EC2 autoscaling
  - Horizontal vs vertical scaling
  - Connect to EC2 instance via SSH key paris
  - Remember EC2 instances deployed in a datacenter that resides in an AZ which resides in a Region
    - A single region contains mutliple AZs
    - A single AZ contains mutliple datacenters
    - A single datacenter containers mutliple servers
    - Servers are physical h/w running in a datacenter
    - EC2 instances are virtual servers running on physical servers.  These instances are not considered serverless.
    - Region (N. Virginia) -> AZ (US-EAST-1) -> datacenter
  - AWS Console - You're able to configure and manage your instances via a web browser.
  - SSH allows you to establish a secure connection to your instance from your local laptop. 
  - EC2 Instance Connect (EIC).  EIC allows you to use IAM policies to control SSH access to your instances, removing the need to manage SSH keys.
  - AWS Systems Manager - Systems Manager allows you to manage your EC2 instances via a web browser or the AWS CLI.
- Lambda - Lambda is a serverless compute service that lets you run code without managing servers.
  - Author application code called functions
    - Supports popular programming languages: Java, GO, PowerShell, Node. JS, C#, Python, and Ruby
  - Scales automatically
  - Serverless means you don't worry about managing servers like EC2 instances
  - Executes code in response to events
  - 15 minute timeout
  - Pricing Modle
    - Compute Time
    - Request Count
    - 1 million always free lambda calls
- Fargate - Fargate is a **serverless compute engine** for containers
  - Manage containers like docker
  - Scale automatically
  - Serverless so you don't worry about managng instances
- Lightsail - Lightsail allows you to quickly launch all the resources you need for small projects. Lightsail is a **compute** service
  - Deploye preconfigured apps like wordpress
  - Easy to use - simple screens
  - Includes VM, ssd storage, data transfer, DNS Managment, static IP
  - Provides low predictable monthly fee
- Outposts - Outposts allows you to run cloud services in your internal data center. Support for hybrid deployments
  - Workloads on-premise due to low-latency or data sovereignty
  - AWS Delivers and installs serverers in customer data center
  - Hybrid experience
  - Access cloud services and APIs to develop apps on-premise
- Batch - Batch allows you to process large workloads in smaller chunks (or batches).  Batch is a **compute** service.  Dynamically provisions instances based on volumes

#### Storage
Companies today need to collect, store, and analyze the data they've accumulated over the years on a massive scale. Storage services in the cloud provide a place for companies to store data.  

- S3 - Simple Storage Service - S3 is an **object storage service** for the cloud that is highly available.
  - Objects (files) are stored in buckets (folders)
  - Unlimted storage
  - Objects can be public or private
  - upload objects, via console, CLI or programatically with code using SDK
  - Set security at bucket or individual object level using ACL, bucket policies or access point policies
  - Enable versioning
  - S3 Access logs
  - Regional service, but must have a globally unique names
  - Durability - objects are never lost.  S3 has 9 11s durability
  - Availability - S3 standard 4 9s availability
  - Storage Classes
    - S3 standard - general purpose, frequent access, and data stored across multiple AZs
    - S3 Intelligent-tiering - automatically determines most cost effective storage
    - S3 Standard-infrequent Access - long live data infrequently accessed
    - S3 One Zone-infrequent Access - recreatable data
    - S3 Glacier - long term data storage and retrieval
    - S3 Glacier Deep Archive - long term data accessed once or twice a year
    - S3 Outposts - on-prem S3 service when data needs to be kept on-prem
  - Good for:
    - Static website
    - Data archive
    - Analytic systems
    - Mobile apps
- EBS - Elastic Block Storage - EBS is a storage device (called a volume) that can be attached to (or removed from) your instance.
  - Data persists when instances is not running
  - Tied to one AZ
  - only attached to one instance in the same AZ
  - Good for running a database or long-term storage
- EC2 Instance store is physically attached to EC2 instance and cannot be removed.  Faster I/O.  Data is lost when EC2 instance is stopped.  Volumes are ephemeral
- EFS - Elastic File System - EFS is a serverless network file system for sharing files.  Supports Linux systems only.  More expensive than EBS.  Acessible across different AZs in same region
  - Business directories
  - Lift and Shift
- Storage Gateway - Storage Gateway is a hybrid storage service
  - Connect on-premises with the cloud
  - Move backups to the loud
- AWS Backup - Backup helps you manage data backups across multiple data services.  Integrates with EC2, EBS, EFS and more.  Backup plan includes frequency and retention

#### Networking
Networking connects computers together and allows for the sharing of data and applications, around the globe, in a secure manner using virtual routers, firewalls, and network management services.   

- Route 53 - Route 53 is a DNS service that routes users to applications.
  - Domain name registration
  - Performs health checks on AWS resources
  - Supports hybrid cloud architectures
- AWS Direct Connect is a dedicated physical network connection from data center to AWS
  - Dedicated physical network connection
  - Connects your on-premises data center to AWS
  - Data travels over a private network
  - Supports a hybrid environment
  - Good for:
    - Large datasets
    - Business Critical data
    - Hybrid Model
- Amazon Virtual Private Cloud (VPC) - VPC is a foundational service that allows you to create a secure private network in the AWS Cloud where you launch your resources.
  - Private virtual network
  - Launch resources like EC2 instances inside the VPC. In a subnet
  - Isolate and protect resources
  - A VPC spans Availability Zones in a Region
  - VPC - EC2 private subnet -> EC2 Public subnet -> NACL -> Router (route table) -> Internet Gateway -> internet
  - VPC Peering connects to VPCs within AWS.  VPC A <-> VPC Peering <-> VPC B
  - Components of a VPC:
    - AZ
    - VPC
    - Subnet
    - NACL
    - Router
    - InternetGateway
- Virtual Private Network (VPN) - Site-to-Site VPN creates a secure connection between your internal networks and your AWS VPCs. 
  - Similar to Direct Connect, but data travels over the public internet
  - Data is automatically encrypted
  - Connects your on-premises data center to AWS
  - Supports a hybrid environment
  - A Site-to-Site VPN makes moving applications to the cloud easier.
- API Gateway - API Gateway allows you to build and manage APIs.
  - Share data between systems
  - Integrate with services like Lambda


#### Content Delivery
A CDN is a mechanism to deliver content quickly and efficiently based on geographic location.  Latency simply means the time it takes to respond to a request.  Low latency is good!  

- CloudFront - CloudFront is a CDN that delivers data and applications globally with low latency.
  - Content globally available or restrict base on location
  - Speeds up delivery of static and dynamic web content
  - edge locations to cache content
  - Good for:
    - S3 static websites
    - Prevent Attacks - DDOS and geo restictions
    - IP address blocking
  - If data not available at the edge, CloudFront retreives data from the origin
- Amazon Global Accelerator - Global Accelerator sends your users through the AWS global network when accessing your content, speeding up delivery.
  - Improves latency and availability of single-Region applications
  - Sends traffic through the AWS global network infrastructure
  - 60% performance boost
  - Automatically re-routes traffic to healthy available regional endpoints
- S3 Transfer Acceleration - S3 Transfer Acceleration improves content uploads and downloads to and from S3 buckets.
  - Fast transfer of files over long distances
  - Uses CloudFront’s globally distributed edge locations
  - Customers around the world can upload to a central bucket

#### Databases
- Relational Database Service (RDS) - RDS is a service that makes it easy to launch and manage relational databases. Like Amazon Aurora, PostgreSQL, MySQL, MariaDB, Oracle Database, and SQL Server.
  - Offers high availability and fault tolerance using Multi-AZ deployment option
  - AWS manages the database with automatic software patching,  automated backups, operating system maintenance, and more.
  - Launches read replicas across regions to provide enhanced performance and durability
- Aurora - Aurora is a relational database compatible with MySQL and PostgreSQL that was created by AWS.
  - Scales automatically while  providing durability and high availability 
  - Managed by RDS
- DocumentDB - DocumentDB is a fully managed document database that supports MongoDB.
  - Document database
  - MongoDB Compatible
  - Fully managed and serverless
  - non-relational
- DynamoDB - DynamoDB is a fully managed NoSQL key-value and document database.
  - Fully managed and serverless
  - Scales automatically to massive workloads with fast performance
  - non-relational
- ElastiCache - ElastiCache is a fully managed in-memory datastore compatible with Redis or Memcached.
  - In-memory datastore
  - Data can be lost
  - Offers high performance and low latency
- Neptune - Neptune is a fully managed graph database that supports highly connected datasets. Create social media graphs
  - Graph database service
  - Supports highly connected datasets like social media networks
  - Fully managed and serverless
  - Fast and reliable

#### Migration and Transfer
- Database Migration Service (DMS) - DMS helps you migrate databases to or within AWS.
  - Migrate on-premises databases to AWS
  - Continuous data replication
  - Supports homogeneous and heterogeneous migrations
  - Virtually no downtime
  - Good for migrating:
    - Oracle to Aurora MySQL
    - Oracle on-prem to RDS Oracle
    - RDS Oracle to Aurora MySQL
- Server Migration Service (SMS) - SMS allows you to migrate on-premises servers to AWS.
  - Migrates on-premises servers to AWS
  - Server saved as a new Amazon Machine Image (AMI)
  - Use AMI to launch servers as EC2 instances
- DataSync - DataSync allows for online data transfer from on-premises to AWS storage services like S3 or EFS.
  - Migrates data from on-premises to AWS
  - Copy data over Direct Connect or the internet
  - Copy data between AWS storage services
  - Replicate data cross-Region or cross-account 
- Snow Family - The Snow Family allows you to transfer large amounts of on-premises data to AWS using a physical device.
  - Snowcone
    - Smallest member of data transport devices
    - 8 terabytes of usable storage
    - Offline shipping
    - Online with DataSync
  - Snowball and Snowball Edge
    - Petabyte-scale data transport solution
    - Transfer data in and out 
    - Cheaper than internet transfer
    - Snowball Edge supports EC2 and Lambda
  - Snowmobile
    - Multi-petabyte or exabyte scale
    - Data loaded to S3
    - Securely transported

#### Analytics
- A data warehouse is a data storage solution that aggregates massive amounts of historical data from disparate sources.
  - Data warehouses support querying, reporting, analytics, and business intelligence. They are not used for transaction processing.
- Redshift -  Redshift is a scalable data warehouse solution.
  - Data warehousing solution
  - Improves speed and efficiency
  - Handles exabyte-scale data
  - Good For:
    - Data consolidation - When you need to consolidate multiple data sources for reporting
    - Relational Databases - When you want to run a database that doesn't require real-time transaction processing (insert, update, and delete)
- Analytics is the act of querying or processing your data.
- Athena - Athena is a query service for Amazon S3.
  - Query service
  - Analyze S3 data using SQL
  - Pay per query
  - Considered serverless
- Glue - Glue prepares your data for analytics.
  - Extract, transform, load (ETL) service
  - Prepare and load data
  - Helps to better understand your data
- Kinesis - Kinesis allows you to analyze data and video streams in real time.
  - Analyze real-time, streaming data
  - Supports video, audio, application logs, website clickstreams, and IoT
- Elastic MapReduce (EMR) - EMR helps you process large amounts of data.
  - Process big data
  - Analyze data using Hadoop
  - Works with big data frameworks
- Data Pipeline - Data Pipeline helps you move data between compute and storage services running either on AWS or on-premises.
  - Moves data at specific intervals
  - Moves data based on conditions
  - Sends notifications on success or failure
- QuickSight helps you visualize your data.
  - Build interactive dashboards
  - Embed dashboards in your applications
- Analytics are good for:
  - Search data in S3.  Athena helps you query historical data stored in S3 as if they were relational data using standard SQL.
  - Log Analytics. Kinesis helps you analyze logs in near real time for application monitoring or fraud detection.



#### Machine Learning
Artificial intelligence (AI) teaches computers to do things that normally require human intelligence. 
- Rekognition - Rekognition allows you to automate your image and video analysis.
  - Image and video analysis
  - Identify custom labels in images and videos
  - Face and text detection in images and videos
- Comprehend - Comprehend is a natural-language processing (NLP) service that finds relationships in text.
  - Natural-language processing (NLP) service 
  - Uncovers insights and relationships
  - Analyzes text
- SageMaker - SageMaker helps you build, train, and deploy machine learning models quickly.
  - Prepare data for models
  - Train and deploy models
  - Provides Deep Learning AMIs
  - Companies like Netflix and Amazon use machine learning models to recommend movies and products to buy. SageMaker is a great tool for creating these models.
- Polly - Polly turns text into speech.
  - Mimics natural-sounding human speech
  - Several voices across many languages
  - Can create a custom voice
  - Polly could convert the text on a blog post to speech that could then be downloaded or replayed in MP3 format. Audio is often a great complement to written communication.
- Translate - Translate provides language translation
  - Provides real-time and batch language translation
  - Supports many languages
  - Translates many content formats
  - translate allows you to add localization to your applications to support your diverse user base. Translate supports several popular languages.
- Lex - Lex helps you build conversational interfaces like chatbots.
  - Recognizes speech and understands language
  - Build highly engaging chatbots
  - Powers Amazon Alexa
  - Amazon used the same technologies that power Lex to integrate Amazon Alexa with the Echo device.

#### Developer Tools
Software developers use tools to accelerate the  software development and release cycle.
- Cloud9 - Cloud9 allows you to write code within an integrated development environment (IDE) from within your web browser.
- Cloud9 preconfigures the development environment with the needed SDKs and libraries. You can easily write the code for your Lambda function directly in your web browser.   
  - Integrated development environment (IDE)
  - Write and debug code
  - Supports popular programming languages
- CodeCommit - CodeCommit is a source control system for private Git repositories. 
- CodeCommit can be used to manage source code and the different versions of application files.  CodeCommit is similar to GitHub
  - Create repositories to store code 
  - Commit, branch, and merge code
  - Collaborate with other software developers
- CodeBuild - CodeBuild allows you to build and test your application source code.
- CodeBuild allows you to run as many parallel streams of tests as needed, allowing you to deploy your changes to production more quickly. 
  -  Compiles source code and runs tests 
  -  Enables continuous integration and delivery
  -  Produces build artifacts ready to be deployed
- CodeDeploy - CodeDeploy manages the deployment of code to compute services in the cloud or on-premises.
- CodeDeploy eliminates the downtime of your application when deploying a new version due to its rolling deployments.
  - Deploys code to EC2, Fargate, Lambda, and on-premises
  - Maintains application uptime
- CodePipeline - CodePipeline automates the software release process
- When combined with other developer tools, CodePipeline helps development teams implement DevOps practices that automate testing and the movement of code to production. 
  - Quickly deliver new features and updates
  - Integrates with CodeBuild to run builds and unit tests 
  - Integrates with CodeCommit to retrieve source code
  - Integrates with CodeDeploy to deploy your changes
- X-Ray - X-Ray helps you debug production applications.
- X-Ray can help you map requests made to your RDS database from within your application. You can track information about the SQL queries generated and more.
  - Analyze and debug production applications
  - Map application components
  - View requests end to end
- CodeStar helps developers collaboratively work on development projects.
- CodeStar can managed the development pipeline
  - Developers connect their development environment
  - ntegrates with CodeCommit, CodeBuild, and CodeDeploy
  - Contains issue tracking dashboard


#### Deployment and Infrastucture Management  
These services help you quickly stand up new applications,automate the management of infrastructure, and provide real-time visibility into system health.  Infrastructure as Code (IaC).  IaC allows you to write a script to provision AWS resources. The benefit is that you provision resources in a reproducible manner that saves time.  
- CloudFormation - CloudFormation allows you to provision AWS resources using Infrastructure as Code (IaC).
- You can use CloudFormation to automate the creation of EC2 instances in your AWS account.
  - Provides a repeatable process for provisioning resources
  - Works with most AWS services
  - Create templates for the resources you want to provision
- Elastic Beanstalk - Elastic Beanstalk allows you to deploy your web applications and web services to AWS.
- After you upload your Java code, Elastic Beanstalk deploys it and handles capacity provisioning, load balancing, and Auto Scaling. Elastic Beanstalk even monitors the health of your application. 
  - Orchestration service that provisions resources
  - Automatically handles the deployment
  - Monitors application health via a health dashboard
- OpsWorks -OpsWorks allows you to use Chef or Puppet to automate the configuration of your servers and deploy code.
- OpsWorks allows you to define software installation scripts and automate configuration for your application servers.
  - Deploy code and manage applications
  - Manage on-premises servers or EC2 instances in AWS Cloud
  - Works with Chef and Puppet automation platforms
- Study for the Exam
  - CloudFormation
    - Don't forget CloudFormation supports infrastructure automation using Infrastructure as Code (IaC).
  - Elastic Beanstalk
    - Don't forget Elastic Beanstalk is only used to deploy applications to the AWS Cloud — it is not used to deploy applications on-premises.
  - OpsWorks
    - Remember that OpsWorks can deploy applications on-premises, and it also automates infrastructure management using Chef or Puppet.

#### Messaging and Integration
Coupling defines the interdependencies or connections between components of a system. Loose coupling helps reduce the risk of cascading failures between components. Queues are used to implement loosely coupled systems.  Monolithic applications tend to be tightly coupled and microservices tend to be loosely coupled.
- Simple Queue Service (SQS) - SQS is a message queuing service that allows you to build loosely coupled systems.
- SQS lets you build an app that is loosely coupled, allowing components to send, store, and receive messages. The use of a messaging queue helps to improve performance and scalability. 
  - Allows component-to-component communication using messages
  - Multiple components (or producers) can add messages to the queue
  - Messages are processed in an asynchronous manner. 
- Study for the Exam
  - SQS
    - Don't forget messages in queues are processed in FIFO order.
    - Remember that message queues support loose coupling.

There are often times that users of your applications need to be notified when certain events happen. SNS works with CloudWatch when an alarm's metric threshold is breached to send an email.
- Simple Notification Service (SNS) - SNS allows you to send emails and text messages from your applications.
- SNS works with CloudWatch when an alarm's metric threshold is breached to send an email.
  - Send email and text messages
  - Publish messages to a topic
  - Subscribers receive messages
- Simple Email Service (SES) - SES is an email service that allows you to send richly formatted HTML emails from your applications.
- SES allows you to send richly formatted HTML emails in bulk and gain valuable insights about the effectiveness of your campaign.
  - Ideal choice for marketing campaigns or professional emails
  - Unlike SNS, SES sends HTML emails
- Study for the Exam
  - SNS
    - Don't forget SNS sends text messages and plain text emails.
  - SES
    - Remember that SES sends HTML-formatted emails for marketing campaigns.


#### Auditing, Monitoring, and Logging
These services give you insight into how well your systems are performing and help you proactively find and resolve errors. 
- CloudWatch - CloudWatch is a collection of services that help you monitor and observe your cloud resources.
- CloudWatch Alarms can notify you if an EC2 instance goes into the stopped state or usage goes above a certain utilization.
- CloudWatch event rule can notify you when root user API calls are detected in your account indicating root user activity.
  - Collects metrics, logs, and events
  - Detect anomalies in your environmentCreate a CloudWatch event rule to notify you when root user API calls are detected in your account indicating root user activity.
  - Set alarms
  - Visualize logs
- CloudTrail - CloudTrail tracks user activity and API calls within your account.
- You can troubleshoot events over the past 90 days using the CloudTrail event history log to find the specific time an event occurred on a per-Region basis. You can create a custom trail to extend past 90 days.
  - Log and retain account activity
  - Track activity through the console, SDKs, and CLI
  - Identify which user made changes
  - Detect unusual activity in your account

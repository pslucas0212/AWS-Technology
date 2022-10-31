# AWS Technology

[AWS Review Notes Table of Contents](https://github.com/pslucas0212/AWS-Review-Notes)

### AWS Services

#### Compute
- EC2 - Elastic Cloud Compute. EC2 allows you to rent and manage virtual servers in the cloud.  Provision with one click.  Chose pre-configured template from Amazon Machine Image (AMI). Configure and manages EC2 instance from the AWS Management console.  SSH secure connection to laptop.  EC2 Instance Connect (EIC) allows you to use IAM policies to control SSH access without the need to manage SSH keys.  Systems manages connects to EC2 via web browser or AWS CLI.
  - Pricing Options
    - On-demand
    - Spot
    - Reserved Instances
    - Dedicated Hosts
    - Savings plans
  - Features
    - Elastic Load Balance across EC2 instances
    - EC2 autoscaling
  - Horizontal vs vertical scaling
  - Connect to EC2 instance via SSH key paris
- Lambda - Lambda is a serverless compute service that lets you run code without managing servers.
  - Supports popular programming languages: Java, GO, PowerShell, Node. JS, C#, Python, and RUub
  - Executes code in response to events
  - 15 minute timeout
  - Pricing Modle
    - Compute Time
    - Request Count
    - 1 million always free lambda calls
- Fargate - Fargate is a **serverless compute engine** for containers.
- Lightsail - Lightsail allows you to quickly launch all the resources you need for small projects. Lightsail is a **compute** service
- Outposts - Outposts allows you to run cloud services in your internal data center. Support for hybrid deployments
- Batch - Batch allows you to process large workloads in smaller chunks (or batches).  Batch is a **compute** sercie

#### Storage
- S3 - Simple Storage Service - S3 is an **object storage service** for the cloud that is highly available.
  - Set security at bucket or individual object level using ACL, bucket policies or access point policies
  - Enable version
  - S3 Access logs
  - Regional service, but must have a globally unique names
  - Storage Classes
    - S3 standard
    - S3 Intelligent Tiering
    - S3 Standard-infrequent Access
    - S3 One Zone-infrequent Access
    - S3 Glacier
    - S3 Glacier Deep Archive
    - S3 Outposts
- EBS - Elastic Block Storage - EBS is a storage device (called a volume) that can be attached to (or removed from) your instance.
- EC2 Instance store is physically attached to EC2 instance and cannot be removed.  Data is lost when EC2 instance is paused/stopped.  Volumes are ephemeral
- EFS - Elastic File System - EFS is a serverless network file system for sharing files.  Supports Linux sysrems only
- Storage Gateway - Storage Gateway is a hybrid storage service.
- Backup - Backup helps you manage data backups across multiple data services

#### Networking
- Route 53 -Route 53 is a DNS service that routes users to applications.
- Virtual Private Cloud (VPC) - VPC is a foundational service that allows you to create a secure private network in the AWS Cloud where you launch your resources.
- Virtual Private Network (VPN) - Site-to-Site VPN creates a secure connection between your internal networks and your AWS VPCs. 
- Direct Connect - Direct Connect is a dedicated physical network connection from your on-premises data center to AWS.
- API Gateway - API Gateway allows you to build and manage APIs.

#### Content Delivery
- CloudFront - CloudFront is a CDN that delivers data and applications globally with low latency.
  - S3 static websites
  - Prevent Attacks - DDOS and geo restictions
  - IP address blocking
- Global Accelerator - Global Accelerator sends your users through the AWS global network when accessing your content, speeding up delivery.
- S3 Transfer Acceleration - S3 Transfer Acceleration improves content uploads and downloads to and from S3 buckets.

#### Databases
- Relational Database Service (RDS) - RDS is a service that makes it easy to launch and manage relational databases.
- Aurora - Aurora is a relational database compatible with MySQL and PostgreSQL that was created by AWS.
- DocumentDB - DocumentDB is a fully managed document database that supports MongoDB.
- DynamoDB - DynamoDB is a fully managed NoSQL key-value and document database.
- ElastiCache - ElastiCache is a fully managed in-memory datastore compatible with Redis or Memcached.
- Neptune - Neptune is a fully managed graph database that supports highly connected datasets.

#### Migration and Transfer
- Database Migration Service (DMS) - DMS helps you migrate databases to or within AWS.
- Server Migration Service (SMS) - SMS allows you to migrate on-premises servers to AWS.
- DataSync - DataSync allows for online data transfer from on-premises to AWS storage services like S3 or EFS.
- Snow Family - The Snow Family allows you to transfer large amounts of on-premises data to AWS using a physical device.

#### Analytics
- Redshift -  Redshift is a scalable data warehouse solution.
- Athena - Athena is a query service for Amazon S3.
- Kinesis - Kinesis allows you to analyze data and video streams in real time.
- Glue - Glue prepares your data for analytics.
- Elastic MapReduce (EMR) - EMR helps you process large amounts of data.
- Data Pipeline - Data Pipeline helps you move data between compute and storage services running either on AWS or on-premises.


#### Machine Learning
- Rekognition - Rekognition allows you to automate your image and video analysis.
- Comprehend - Comprehend is a natural-language processing (NLP) service that finds relationships in text.
- SageMaker - SageMaker helps you build, train, and deploy machine learning models quickly.
- Polly - Polly turns text into speech.
- Translate - Translate provides language translation
- Lex - Lex helps you build conversational interfaces like chatbots.

#### Developer Tools
- Cloud9 - Cloud9 allows you to write code within an integrated development environment (IDE) from within your web browser.  
- CodeCommit - CodeCommit is a source control system for private Git repositories.  
- CodeDeploy - CodeDeploy manages the deployment of code to compute services in the cloud or on-premises.
- CodeBuild - CodeBuild allows you to build and test your application source code.
- CodePipeline - CodePipeline automates the software release process
- X-Ray - X-Ray helps you debug production applications.

#### Deployment and Infrastucture Management
- CloudFormation - CloudFormation allows you to provision AWS resources using Infrastructure as Code (IaC).
- Elastic Beanstalk - Elastic Beanstalk allows you to deploy your web applications and web services to AWS.
- OpsWorks -OpsWorks allows you to use Chef or Puppet to automate the configuration of your servers and deploy code.

#### Messaging and Integration
- Simple Queue Service (SQS) - SQS is a message queuing service that allows you to build loosely coupled systems.
- Simple Notification Service (SNS) - SNS allows you to send emails and text messages from your applications.
- Simple Email Service (SES) - SES is an email service that allows you to send richly formatted HTML emails from your applications.

#### Auditing, Monitoring, and Logging
- CloudWatch - CloudWatch is a collection of services that help you monitor and observe your cloud resources.
- CloudTrail - CloudTrail tracks user activity and API calls within your account.

# AWS Technology

[AWS Review Notes Table of Contents](https://github.com/pslucas0212/AWS-Review-Notes)

### AWS Services

#### Compute
- EC2 - Elactic Cloud Compute. EC2 allows you to rent and manage virtual servers in the cloud. 
- Lambda - Lambda is a serverless compute service that lets you run code without managing servers.
- Fargate - Fargate is a serverless compute engine for containers.
- Lightsail - Lightsail allows you to quickly launch all the resources you need for small projects.
- Outposts - Outposts allows you to run cloud services in your internal data center.
- Batch - Batch allows you to process large workloads in smaller chunks (or batches).

#### Storage
- S3 - Simple Storage Service - S3 is an **object storage service** for the cloud that is highly available.
- EBS - Elastic Block Storage - EBS is a storage device (called a volume) that can be attached to (or removed from) your instance.
- EFS - Elastic File System - EFS is a serverless network file system for sharing files.
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


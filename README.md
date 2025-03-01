# Re-Architecting Multi-Tier Web Application Stack on AWS
### Introduction
This project involved migrating a multi-tier web application stack to AWS by boosting agility ,reliability, security. This project addresses varies problems like Operatinal Overhead, Stuggling with uptime & Saling and Regular OpEX.AWS services Utilized are Elastic Compute Cloud(EC2), Simple Storage Service(S3), AWS Beanstalk, Elastic Load Blancer, Relatinal Database Service(RDS), Amazon Elasticache, Amazon MQ, Route 53, Amazon Cloud Front and Amazon CloudWatch 

### Architecture
![WhatsApp Image 2025-02-28 at 19 33 32](https://github.com/user-attachments/assets/712f14c1-d511-44ff-8074-2b755bd7432c)

When a user accesses the URL, it resolves to an endpoint managed by Amazon Route 53. This endpoint directs the request to Amazon CloudFront, which then forwards it to an Application Load Balancer (ALB). The ALB distributes traffic across an Auto Scaling Group running a Tomcat application within AWS Elastic Beanstalk. Amazon CloudWatch continuously monitors the Auto Scaling Group, ensuring EC2 instances scale as needed. Application artifacts are stored in an Amazon S3 bucket.

For the backend, the architecture includes Amazon MQ for messaging, Amazon ElastiCache for caching, and Amazon RDS for database management.

### Steps Invloved
• Create Key pair for beanstalk instance login

• Create Security Group for Elasticcache, RDS & ActiveMQ

• Create RDS, AmazonElastic Cache and Mazon MQ

• Create Elastic Beanstalk Environment

• Update SG of backend to allow traffic from Bean SG

• Update SG of backend to allow internal traffic

• Launch Ec2-Instance for DB Initializing
• Login to the instance and Inititialize RDS DB
• Change healthcheck on beanstalk to /login
• Add 443 https Listner to ELB
• Build Artifact whith Backend Information
• Deploy Artifact to Beanstalk
• Create CDN with SSL certificate
• Update Entry in GoDaddy DNS Zones
• Test the URL

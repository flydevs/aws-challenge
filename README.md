## Regions and Availability Zones
The AWS cloud is made up of regions and availability zones. 

### Regions 
Regions are simply areas all araound the world and there are currently 15 regions that exists plus GovCloud. These are dynamic and they are constantly changing. A region for Africa has been anticipated soon and there other regions are being on boarded as we speak. And an important thing to understand about regions is they may or may not provide all of the services. 
AWS rolls out new services introducing them to a single region or maybe a small subset of regions and then over time that service will be propagated to additional regions. This may factor into your decision as to where you want to place your AWS resources within regions. 
1. Simply a geographic area.
2. 15 regions currently exist, plus GovCloud.
3. These are dynamic, and change over time.
4. A region for Africa is anticipated soon.
5. May not provide all services.

### Availability Zones
Within regions we have availability zones, these are groups of datacenters within a region. An availability zone can have as few as one data center or as many exists. There's going to be two or more available zones inside of each region.   
1. Datacenters within a region.
2. Two or more per region.

### CloudFront
Now on top of that we also have CloudFront Edge locations that are spread all over the world. Web sites are delivered from the nearest edge location. This improves the overall performance of services by allowing you spread Web Resources over a vast array of physical locations all over the world. That's how cloud front provides improved performance and it can also potentially reduce your costs. So cloudfront supports other AWS features including S3, it supports EC2 which you can use to run a web server, it supports Elastic Load Balancers and DNS (Route53).

1. Edge locations are spread across the globe.
2. Websites are delivered from the neares edge location.
3. Improves performance.
4. Also supports other AWS features:
  * S3 - Amazon Simple Storage Service.
  * EC2 - Amazon Elastic Compute Cloud.
  * Amazon Elastic Load Balancing.
  * DNS - Amazon Route 53 

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html
https://aws.amazon.com/es/about-aws/global-infrastructure/

### Service Offerings of AWS
AWS is broken up into multiple regions all over the world and within each regions there are multiple availability zones that provide us with high availability within that AWS region. And there's also a vast number of cloud an edge locations spread all over the world. Now all this AWS global infrastructure is used to provide the service offerings that are include within AWS and you can find the full list of product offerings [here](https://aws.amazon.com/products/)

#### Virtual Private Cloud (VPC) - Networking
For networking we got a number of different solutions available. We're going to refer to this as the Virtual Private Cloud that's going to give us segmentation between us and the other customers within AWS. That's what a VPC is. We can control IP Address, ranges, subnet, routing tables, network gateways, we can support IP version 4 and IP version 6.
1. Many different entities are served by the AWS Cloud.
2. How do we provide segmentation?
3. Your VPC is a logically isolated section of AWS with your own virtual network.

#### Route53
We can use Route53 for DNS, that is a web based DNS Service. It resolves fully qualified domain names like wwww.google.com to a certain IP address. It provides FQDN(fully qualified domain name) to IP address translation and it can also monitor health of your servic es and route away from them if you're experiencing an outage.
1. Web Based DNS.
2. Provides FQDN to IP address translation.
3. Provides health monitoring.

### EC2 (Elastic Compute Cloud)
This is how we can run virtual servers on AWS. We can spin up what are called EC instances and run Windows or Linux on them and then we can install whatever applications we want on top of those virtual servers that we refer to as EC instances. 
1. Alternative to physical compute capacity.
2. An EC2 instance is a virtual server.

### Elastic Beanstalk
Allows you to bring your own code and deploy it using AWS resources, even if you are not that familiar with AWS, you simply upload your code and AWS builds the required resources including high availability and load balancing for that application.
1. Deploy Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker applications.
2. Developers upload their code, and Amazon takes it from there.

### Lambda
Is one of the hottest topics within AWS, what it allows you to do is run your code without even have a virtual server. It's called server-less and it can result in significant cost savings versus EC2. You simple upload your code and Lambda takes it from there including scaling and high availability. 
1. Run code without a VM.
2. Significant cost savings vs. EC2.
3. Easy to use.

### S3 (Simple Storage Service)
It is an object based storage solution, kind of like Dropbox of AWS and it's extremely durable providing eleven nines of durability. It's commonly used to store analytics data files backups and disaster recovery data. 
1. Simple file storage.
2. Designed to deliver 99.999999999% durability.
3. Many use cases. 

### RDS (Relational Database Service)
This is a way that you can run your relational database in the cloud. It supports database engines like Oracle, or Sequel or Amazon Aurora and it makes it very easy to create a database that is highly scalable and easily to managed. It frees you up from many of those common time consuming database management tasks like patching backups, and it provides a wide variety of database engines. 
1. Relational database in the Cloud.
2. Easy to deploy and manage.
3. Provides familiar database engines.

### DynamoDB
This is a managed No-SQL database service, I mean a non-relational database.This is useful for applications that need consistent single digit milisecond latency regardless of scale. Things like web and gaming applications, IoT and similar use cases.
1. NoSQL, non-relational database solution.
2. High-performance regardless of scale.
3. Use cases include mobile, web, gaming, and IoT applications and more.

### IAM (Identity and Access Management)
IAM is used to control users groups and roles within AWS. And withing IAM you can set password retention policies, you can configure multi factor authentication as well. You can also configure really fine grained access rules like the time of day that a user can access the AWS console or acceptable source apis.
1. Control users groups, and roles within AWS.
2. Configure password policies and MFA.
3. Create fine-grained rules.  

### Managed vs Unmanaged
Let's start with the most commonly used example: EC2 vs RDS
EC2 is an unmanaged service, that means that I'm gonna have to do a lot of stuff manually. I'm gonna have to scale EC2 instances manually. I have to figure out my configuration for high availability and for clustering and patching and backups and managing the operating system. All of those things are manual tasks that I need to perform on EC2 instance, I mean if I don't update windows or linux, it's not going to happen, final install the latest patches, if I don't configure some kind of high availability solution myself, EC2 is not going to have those features. 
Whereas RDS is a managed service, is used for database instances and in this case AWS provides the operating system. AWS provide the database engine, they do all the patching and upgrades and all that sort of stuff. It comes with a built in, high availability solution using multi-AZ RDS, yes it comes with a built in clustering solution using read replicas. So a lot of the features that I would have to manually configure an EC2 I don't have to manually configure in RDS. All I really need to do is maintain my database clients and my queries and use the features that AWS has already provided to me. 
So that's really the biggest difference between a managed and unmanaged service so the other thing that we need to bear in mind with RDS is that is a managed service and we're giving up some level of control there, well AWS owns and manage that operating system, I don't have root level access to it, I can't do some of the things that I could do on a EC2 intance. So that's really the tradeoff, when it comes to managed vs unmanaged service. Within unmanaged service you have full control, you have root level access whereas with an managed service you have a lot of less work to do. 
Services that Allow Root Access:
1. EC2.
2. EMR, Elastic Map Reduce which is our Hadoop cluster service.
3. Elastic Beanstalk which is used to deploy code and automatically create resource for us.
4. OpsWorks.
Managed Service Examples:
1. S3.
2. DynamoDB.
3. RDS.
4. NAT Gateway.

### Benefits of Managed Services
There are bennefits of managed services, they're more secure, they're easier to manage of course and I don't have to worry about things like patching and backups and all that sort of stuff that we typically have to worry about with the operating system because we have control of the service but not control of the underlying operating system. And with the managed services AWS is going to provide us with high availability for example S3 stores data across three data center, already yes give us multi-AZ RDS so there are built in high availability solutions to these managed services.
1. More Secure.
2. Easier to Manage.
3. Don't have to worry about backups, patches, etc...
4. You control the service, but not the underlying O.S.
5. AWS provides high availability.

### Benefits of Self-Managed Services
Now when it comes to unmanaged services or self-managed services, our big benefit there is we have full control. We have root level access to the operating system. We can do whatever kind of optimization that we want. Whatever kind of modification we want to the operating system and we can also support any application. So for example MongoDB, there is not a managed service for that but I can run it on a EC2 intance which is an unmanaged service. 
1. Control.
2. Optimization beyond managed services.
3. Support any application (I.E. - Mongo DB).
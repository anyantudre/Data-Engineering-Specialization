## Data Engineering on the Cloud

some of the core AWS services breaken up into five categories, compute, network, storage, databases, and security.

### compute
- Amazon elastic compute cloud or EC2: the service that provides virtual machines or VMs on AWS. 
a VM as a virtual computer or server where you can run whatever operating system you want, like Linux, macOS or Windows, as well as any applications, just like you would on any computer.

But in this case, on the AWS cloud when you launch a single VM using EC2, we call that an Amazon EC2 instance:
    - complete control over that instance, including the operating system, applications and anything else that happens on the instance itself. 
    - very flexible option for your workloads that offers you a lot of control:
        - as a development machine for programming
        - run a web server or containers or 
        - machine learning workloads or whatever you want. 
    - You can deploy a single EC2 instance or a fleet of them and scale horizontally to match demand. So that's a very quick rundown on EC2. 

Different options for compute on AWS:
- serverless functions using a service called AWS lambda, which is where you can host code that runs in response to triggers or events
- container hosting services like Amazon Elastic Container Service or Amazon Elastic Kubernetes Service.

Réf: https://www.coursera.org/learn/intro-to-data-engineering/supplement/fyNJD/compute-amazon-elastic-compute-cloud-ec2


### networking

Whenever you create an EC2 instance or many other types of AWS resources, you need to place it into a network of some kind. 

Amazon Virtual Private Cloud or VPC for short are private networks in the cloud that you can create and control that are isolated from other networks in the AWS cloud in which you can create and place resources. 
You choose the size of the private IP space you want and you can partition it into smaller networks called sub networks or subnets for short. A single VPC spans all availability zones within a region, but you cannot span across regions. So youd need to create a VPC in every region you want to operate in. 
The same is true for most AWS resources, they are region bound. So whenever you create certain AWS resources, like EC2 instances or instance based databases, you need to select which VPC you want and which AZ you want to place it in. 

Réf: https://www.coursera.org/learn/intro-to-data-engineering/supplement/MMwyn/networking-virtual-private-cloud-vpc-subnets


### storage

- object storage: most often used for storing unstructured data like documents, logs, photos, or videos. But really, you can put any kind of data into object storage
Amazon S3 object storage service

- block storage: which is typically used for database storage, virtual machine file systems, and other environments where low latency and high performance are critical. 
Within AWS, you can attach block storage devices called Amazon elastic block store volumes to EC2 instances which mount to the os, and you can then store and access data using programs running on EC2.

- file storage: which is the most familiar type of storage for your average non technical user. With file storage, data is organized into files and directories in a hierarchical structure, just like your file system on your laptop or a shared file system at work. 
AWS has a managed service called Amazon Elastic file system, which provides a scalable file storage solution that can be mounted to multiple different systems at once for file access.


- In some sense, you could say databases are just another kind of storage service, but databases fall into a separate core category. Though databases use block storage behind the scenes to store data, they also provide special functionality for managing structured data, like enabling complex querying, data indexing, and other features which are not typically offered by general storage services. 
As a data engineer, you will frequently work with tabular data organized in relational database format. 
- Amazon relational Database service, or RDS, which, as the name implies, is a cloud based relational database service. 
- Amazon Redshift, which is a data warehouse service that allows you to store transform and serve data for end use cases.



### security 
AWS follows what we call the shared responsibility model. The shared responsibility model states that AWS is responsible for security of the cloud and you are responsible for security in the cloud. 


Réf: https://www.coursera.org/learn/intro-to-data-engineering/supplement/uqYtR/security-aws-shared-responsibility-model

Week 1 Resources: https://www.coursera.org/learn/intro-to-data-engineering/supplement/WFANk/week-1-resources
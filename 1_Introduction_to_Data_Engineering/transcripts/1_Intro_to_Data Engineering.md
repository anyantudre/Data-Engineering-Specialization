## High level look at the field of data engineering

### Context:
In the last decade, pretty much every industry has become digital. Digital communications are pervasive, and digital data is replacing pieces of paper as the primary mechanism for information is stored in healthcare, finance, manufacturing, education, tech, and pretty much all industries. But with this tidal wave of data comes risk and also new challenges for how to store and process all those data to create value. Whether your organization is looking to improve how it serves customers or outmaneuver the competition, having good data pipelines is increasingly critical, which is why there's also skyrocketing demand for data engineers. 


### particular scenario:
company first hired a data scientists because they were interested in doing analytics to learn more about their customer interests, behaviors, and purchasing habits. They also wanted to develop machine learning tools using large language models to automate various aspects of customer support. However, when this poor data scientists got started, they discovered that none of the data infrastructure they needed to tackle the analytics or machine learning tasks even existed yet. They quickly started studying up on data architectures and systems to try to help build the infrastructure they needed. But also explain to those in leadership that building data infrastructure was not their forte and optimize for success, the company should also hire a data engineer. That's where you come in. 

Now, this might sound a really silly story, but I can't tell you how many times I've seen this exact scenario played out in real life. In fact, I was one of those data scientists who got hired by a company just like the one I described. I found myself thrown into a situation where I needed to quickly learn how to build various aspects of data infrastructure, just to get the company's data and systems into a state where I could begin working on the data science projects. And as I dove into designing and building data systems, I was both overwhelmed and excited by what I was learning. I discovered that the set of core skills to build robust data infrastructures was largely the same, no matter what sort of downstream tasks you're trying to accomplish when it comes to things like data science and machine learning, as well as other things like delivering embedded analytics to users within applications. Over time, that core set of skills has come to be known as data engineering.


### Recovering Data Scientist:
Recovering data scientist is, I guess, a nickname I was given back in maybe the mid-2010s. This is about the time when data science was becoming very hot and popularized. My background was in machine learning, analytics, and similar roles. What I had noticed was companies were hiring data scientists without giving them the proper support and foundational infrastructure to succeed at their jobs. It'd often be going into a job as a data scientist with no data upon which to do the science. Seeing this over and over again, I started realizing that what was also important to help data science succeed was data engineering. And so this is about building the foundation of infrastructure, data quality, and providing the means for a data scientists to succeed at their job. Although I got my start in data science, I moved into data engineering to help solve these problems for data scientists.

Réf: https://www.linkedin.com/pulse/what-recovering-data-scientist-joe-reis/

### Data Centric AI:
Data-centric, as you all know, is the discipline of systematically entering the data, the build a successful AI system. I think for dataset sizes ranging from that small CSV file on your laptop to the massive dataset stored in dataware houses, including the way that large language model is trained today with trillions of tokens, the ability to engineer the data to get the AI of the machine learning m, the data it needs to succeed.


### Why you should always start by looking at the big picture
You've just been hired as a data engineer, and your company is looking for you to build data systems that can deliver on their goals. To accomplish this, you'll need to be able to translate the needs of the stakeholders in your company into system requirements and then choose the right set of tools and technologies to build that system. Now, that might sound relatively straightforward. But all too often, I've seen data engineers dive straight into the implementation of a system, choosing tools and technologies before they deeply understood how their systems will deliver value for the organization. Taking such an approach can lead to disaster, like wasting time, resources at your company, and could even cost your job. Rather than diving straight into implementation here, in these courses, particularly in this first course, we'll be spending a fair amount of time looking at the big picture. Talking about a set of principles that will apply to all of your data engineering projects.



### How data engineering role born?
The field of data engineering change over time. 
The original data engineers were software engineers, whose primary work was building the software applications or organizations needed. And not that long ago. The data being generated by those software applications was mostly regarded as a byproduct or exhaust. What I mean by that is, let's say you have a software application running over here like this, and it's recording various events within this application to a log. Then this data recorded in the log might have been considered useful for things like troubleshooting or monitoring the health of the application. But it wasn't thought of as having much intrinsic value on its own. I'll draw this little exhaust pipe coming out of the application, and then you'll have data being generated like the exhaust from a car or really just a byproduct of the application. 
Over time, however, as organizations began to recognize the intrinsic value of data. As a volume and variety of data being generated by software applications, uploaded by users or created through the digitization of various records continued to grow, those same software engineers became increasingly focused on building systems specifically for the purposes of ingesting, storing, transforming, and serving data for various use cases. With the emergence of data engineering as a central function within many organizations that work with data, the role of data engineer was born.



### What is Data Engineering?
In the book Fundamentals of Data Engineering

"Data engineering is the development, implementation, and maintenance of systems and processes that take in raw data and produce high quality consistent information that supports downstream use cases, such as analysis and machine learning. Data engineering is the intersection of security, data management, DataOps, data architecture, orchestration, and software engineering."

In simpler terms, your job as a data engineer is to get raw data from somewhere, turn it into something useful and then make it available for downstream use cases.


### Data engineering lifecycle:
You can think of the data engineering life cycle as comprising a series of stages. On the left here, you have data generation and source systems. These source systems might be any kind of software application or user generated data or sensor measurements, or something else. One way or another, the life cycle starts with data generation. Then in the middle here, you have ingestion, transformation, storage, and serving. I've drawn a box around these stages to indicate that these are the stages of the life cycle that will be your focus as a data engineer. Notice here that storage sits underneath ingestion, transformation, and serving and spans the entire width of the box. This is to indicate that data storage is an integral part of each of the stages above. In practice, the data systems you build may not look quite as simple as a life cycle diagram might appear. But in my experience, it's helpful to think of the life cycle in this way when it comes to visualizing the common elements of any data system. On the right side of the diagram, you have the end use cases. These are the ways in which stakeholders in your organization will actually derive value from the data. These include things like analytics, machine learning, or something called Reverse ETL, which is basically sending the transformed or processed data back to the source systems to provide additional value for individuals in an organization who use these systems. 


### A Brief History of Data Engineering
Data has always existed, but data engineering refers mainly to **digitally recorded data**.

* **1960s–70s**: Birth of computerized databases, relational databases, and SQL (developed at IBM).
* **1980s**: Bill Inmon creates the first **data warehouse** for analytical decision-making.
* **1990s**: Growth of business intelligence; Inmon and Ralph Kimball propose different **data modeling approaches**. The **Internet boom** spurs servers, databases, and storage systems.
* **2000s**: Survivors of the dotcom bust (Google, Amazon, Yahoo) face **explosive data growth**, marking the **big data era** (defined by volume, velocity, variety).
  * **2004**: Google publishes the **MapReduce paper**, inspiring Yahoo to create **Apache Hadoop** (2006), catalyzing large-scale data processing.
  * **Amazon** builds scalable infrastructure: **EC2 (compute)**, **S3 (storage)**, **DynamoDB (NoSQL)**, launching **AWS**, the first major **public cloud**. This “pay-as-you-go” cloud model revolutionizes software and data systems.
* **Late 2000s–2010s**:

  * Democratization: startups gain access to cutting-edge data tools.
  * Transition from **batch computing** to **event streaming** enables **real-time data**.
  * Challenges: managing big data stacks (Hadoop, etc.) required costly, complex operations.
  * Eventually, “big data engineers” simply became **data engineers**, as scalable processing became mainstream.
  * Rise of **Cloud-first**, **open source**, and **third-party products** simplified large-scale data work.
* **Today**:

  * Data engineering emphasizes **integration and orchestration** of diverse technologies (“Lego bricks”) to meet **business goals**.
  * The role has moved **up the value chain**: data engineers now directly support **business strategy**, leveraging mature tools and contributing to future innovations.
  * Every company seeks to derive value from data, regardless of size.

In short, data engineering has evolved from maintaining complex big data systems to **strategically building robust, scalable, business-driven data platforms**, central to modern organizations.



### The Data Engineer Among Other Stakeholders:
In order to know exactly how to turn raw data into something that is useful for downstream consumers, you have to deeply understand their needs. If you're successful as a data engineer, you'll be serving data to downstream users in a way that adds value for them and helps them achieve their goals.

We've already mentioned some of these potential end use cases, namely analytics and machine learning. When it comes to who the downstream data consumers are. In each of these cases, these could be analysts, data scientists, machine learning engineers, or others in your organization who need to make data driven decisions like salespeople, product or marketing professionals, or executives. 

In addition to downstream stakeholders, you'll also have upstream stakeholders to take into consideration. Upstream stakeholders are those people responsible for the development and maintenance of the source systems you ingest raw data from. Your upstream stakeholders are often the software engineers who build the source system you're working with. And these might be software engineers within your company or they could be the developers responsible for a third party source you're ingesting data from. 
In this case, you would need to communicate with the source system owners to understand what you can expect in terms of volume, frequency and format of the generator data and anything else that will impact the data engineering lifecycle, such as data security and regulatory compliance.

So to recap, in your efforts to get raw data and turn it into something useful and serve it to end use cases, you'll have stakeholders both downstream and upstream of the systems you build. Take the time to connect with those upstream source system owners to better understand the data you're ingesting, as well as anything that might disrupt your data pipelines like outages or changes in the data. And when it comes to downstream stakeholders, take the time to understand how the data you're serving adds value for your organization and how that relates to the individual goals of the stakeholders you serve. 


### Business Value:
Bill Inman, one of the thought leaders and most knowledgeable people in the field of data advice he would give someone who is starting out in the industry(he emphasized the importance of finding and delivering business value. ):

"I'm going to give them the same advice as if they were a bank robber. Go to where the money is if you want to have long term, great success in our industry, find business value. Don't get hung up on every technology that comes out. Every new fangled thing that comes out, go to where there's business value. Because at the end of the day, business value drives everything we do in technology. And it's easy to get lost and hung up on technology. And there's nothing wrong with technology. Heck, I'm a technician myself, I love technology. But the number one thing you need to think about now, if you don't care about success and you want to go off and do some fancy stuff that looks interesting and whatever, then go ahead and do it. But don't expect to have any great reward for what you've done."


But what does it actually mean to add value as a data engineer? Well, in my experience, business value is somewhat, you might say, in the eye of a beholder.

And what I mean by that is, for example, suppose your organization is hoping that your work as a data engineer can help with revenue growth. In this case, if your manager or those in leadership perceive your work as contributing to the growth of revenue for the company, then congratulations, it's highly likely you'll be recognized as adding value for the organization. On the other hand, if your work as a data engineer is perceived as simply costing large sums of money with little or no return on investment, then you might need to start looking for another job. But in many cases, business value is not just as simple as profit and loss. It takes many different forms, as we looked at in the previous video. In your work as a data engineer, you'll interact with various stakeholders. Oftentimes, it'll be those stakeholders who decide for themselves whether you're adding value. And in general, that means whether or not they perceive you as helping them achieve their goals. Notice that in all these examples, I'm talking about how your work is perceived rather than what it is that you actually do. The amount of value you provide for the business and the stakeholders, will be determined by those to whom you are providing that value. And so in general, when you're fulfilling stakeholder needs, you're providing them with value, whether that comes in the form of increased revenue, cost savings, work made more efficient, or something else, like helping with a successful product launch. 


Multiple forms for business value:
• Increased Revenue 
• Cost Savings  
• Improved efficiency 
• Launch a product

### Requirements:

First off, the word requirements can mean a number of different things in the context of business and engineering. 
- You can have business requirements, for example, that define the high level goals of the business. Business requirements might broadly include things like growing revenue or increasing the user base. 
- Stakeholder requirements, on the other hand, are the needs of individuals within the organization, namely those things they need to get their job done well. 

When it comes to data engineering or software development in general, Engineers need to define system requirements that describe what a system needs to be able to do in order to meet the business and stakeholder requirements. 
- System requirements 

two categories, functional and non functional requirements, which you can think of loosely as the what and the how requirements for your system respectively. 
    - Functional requirements or the what, meaning those things that the system needs to be able to do. In the context of data engineering, these might be things like providing regular updates to a database that serves analytics dashboards or alerting a user when there's an anomaly in the data. 
    - By contrast, you can think of non functional requirements as how your system will accomplish what it needs to do. This could include things like technical specifications for ingestion, orchestration, or storage that you plan to use within your data pipelines to meet the end users' needs. To build any data system, you need to start with a set of requirements for that system. These could include everything from high level business and stakeholder requirements, to features and attributes of the data products you provide, right down to the memory and storage capacity you need for your computation and database resources. You'll also have cost constraints, as well as security and regulatory requirements to consider. 
    
The first and most important step in any data engineering project is to gather the requirements for your system. In general, those requirements will come from your downstream stakeholders, those that hope to achieve their goals as a result of your work. The problem is your stakeholders will most often not be speaking to you in the form of concrete system requirements. Instead, what they have on their minds are business goals, and it's your job to figure out how to translate their needs as they relate to the business goals into the requirements for your system. Requirements gathering is going to look a little different for every system you build. But this process always starts with having conversations with your stakeholders.



### Translate Stakeholder Needs into Specific Requirements:
- First, learn what existing systems or solutions are in place to deliver the data your stakeholders need to accomplish their tasks, and also what the pain points or problems are with those systems. 
- Next, learn what actions stakeholders plan to take based on the data you serve them. 
- And after that, repeat what you learned back to your stakeholders to confirm that you understood everything correctly. - - And finally, identify any other stakeholders you'll need to talk to if you're still missing information on existing systems or planned actions.

From data scientists side:
    - the marketing team needs real time analysis of product sales by region, but they are only getting a daily data dump from the software team to avoid compromising the production database. 
    - sometimes they experience problems due to schema changes or other anomalies in the data. When it comes to data schema changes or other disruptions to your source system, you could be thinking about how to build in automatic checks on the data you're ingesting to ensure that it looks like everything meets expectations.
    - the cumbersome nature of data cleaning and processing (automate the ingestion and transformation of data into the format they require)
    - marketing team needs the data in real time.

From Source system owners who are serving that data(with the software engineers who maintain the source system and database you'll be ingesting data from)
    - aim to understand what an ingestion solution might look like that is better than the daily data dumps, as well as 
    - what kind of disruptions or changes you can expect and how you might be given advanced notice of when to anticipate those changes.

- Functional requirement in that the system needs to ingest, transform and serve the data in the format your data scientist needs. 
- The non functional requirements for this aspect of your system might include things like a latency requirement about how fast the data needs to be made available relative to when it was recorded in the source system. 


### framework for thinking like a data engineer

In this first stage, your main objective is to determine what the business goals and stakeholder needs are, that will be driving a project. 
- get clear on the high level business goals for the company
- identify who all of the stakeholders are that have needs related to your project and how their needs tie into those higher level business goals. 
- have conversations with individual stakeholders, learn what systems are currently in place that you'll either be building or replacing and what needs stakeholders have beyond what the current systems are providing. 
- ask your stakeholders what action they plan to take with the data products you provide them. This can help you zero in on the actual functional requirements of the system you'll build. 

In the second stage, your objective is to turn stakeholder needs and the functional and non functional requirements for your system. 
- In short, this means describing what the system must be able to do to meet the needs of stakeholders. These are the functional requirements, 
- and then describing the technical specifications of how the system will do what it needs to do, the non functional requirements. Once you've arrived at a set of functional and non functional requirements, you'll document your conclusions and confirm with stakeholders that a system designed to do what you have described in these requirements will meet their needs. 

In the third stage, you'll choose the tools and technologies to build your system. 
- identifying the tools and technologies that can meet the requirements of your system. In general, there will be multiple tools and technologies that can meet any individual requirement, and you'll have to evaluate the trade offs between them. 
- look at a cost benefit analysis to choose the best components among these tools. In this analysis, you may consider things like licensing fees, estimates of spending on Cloud resources, as well as other resources needed to build and maintain a system with these components. 
- prototype of your system to test whether it meets your expectations and looks like it can deliver value for your stakeholders. This last step of standing up a prototype and testing it is very important. Before investing the time and energy into building out the full data system, You need to test whether the system you've designed will actually be able to meet the needs of your stakeholders. At this stage, you'll check back with stakeholders and let them evaluate whether the system you've designed will deliver value for them. And I would definitely recommend that you spend as much time as it takes iterating on your prototype to be sure your system is going to be successful once you move into production. 

As a last step in this final stage, 
-  you'll build and deploy your data system. Once it's up and running, you'll continuously monitor and evaluate your system's performance and iterate on it to keep improving it where you can. Any data system you build will need to evolve over time. This can be due to changing stakeholder needs or in some cases, the emergence of a new tool or technology that can improve your system's performance, reduce your costs, or provide some other advantage. 

And so while I presented this framework as a sequence of four stages that happened one after another, in reality, this will be an ongoing and sort of cyclical process. As business goals and stakeholder needs evolve, your data systems will need to evolve with them. So you can think of this as something where, as a data engineer you're always communicating with stakeholders about their needs and expectations, evaluating those needs in terms of requirements for your data systems, and updating your systems as needed to meet the needs of your stakeholders.



### Data Engineering on the Cloud

some of the core AWS services breaken up into five categories, compute, network, storage, databases, and security.

#### compute
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


#### networking

Whenever you create an EC2 instance or many other types of AWS resources, you need to place it into a network of some kind. 

Amazon Virtual Private Cloud or VPC for short are private networks in the cloud that you can create and control that are isolated from other networks in the AWS cloud in which you can create and place resources. 
You choose the size of the private IP space you want and you can partition it into smaller networks called sub networks or subnets for short. A single VPC spans all availability zones within a region, but you cannot span across regions. So youd need to create a VPC in every region you want to operate in. 
The same is true for most AWS resources, they are region bound. So whenever you create certain AWS resources, like EC2 instances or instance based databases, you need to select which VPC you want and which AZ you want to place it in. 

Réf: https://www.coursera.org/learn/intro-to-data-engineering/supplement/MMwyn/networking-virtual-private-cloud-vpc-subnets


#### storage

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



#### security 
AWS follows what we call the shared responsibility model. The shared responsibility model states that AWS is responsible for security of the cloud and you are responsible for security in the cloud. 


Réf: https://www.coursera.org/learn/intro-to-data-engineering/supplement/uqYtR/security-aws-shared-responsibility-model

Week 1 Resources: https://www.coursera.org/learn/intro-to-data-engineering/supplement/WFANk/week-1-resources
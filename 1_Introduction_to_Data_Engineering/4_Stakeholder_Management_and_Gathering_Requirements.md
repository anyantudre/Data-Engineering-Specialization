# Stakeholder Management and Gathering Requirements
*Building robust data systems by aligning business goals, stakeholder needs, and technical implementation.*

---

### Introduction
Effective data engineering is not only about tools and technologies; it begins with understanding people, processes, and business objectives. This chapter explores the **art of gathering requirements and managing stakeholders**—two foundational skills every data engineer needs to succeed. We will walk through a structured framework that connects business goals, stakeholder needs, and system requirements, while examining conversations with executives, marketing teams, software engineers, and data scientists. From defining functional and non-functional requirements to exploring AWS tools for batch and streaming pipelines, this guide brings together the practical and strategic aspects of data engineering.

---

## Overview
The journey of a data engineer starts with understanding *why* systems need to be built, not just *how*. Early in the course, requirements gathering was introduced as a crucial step. Conversations with data scientists, marketers, and engineers quickly reveal interdependencies across teams.

A guiding framework for data engineers is:

1. **Identify business goals and stakeholder needs**.
2. **Translate needs into system requirements**.
3. **Choose appropriate tools and technologies**.
4. **Design, build, and deploy the system**.

While simple in appearance, each stage requires critical thinking: asking what actions stakeholders plan to take, translating needs into functional and non-functional requirements, and planning for iterative evolution. This chapter pulls all these pieces together in an applied, real-world scenario.

---

## Requirements
Requirements can be visualized as a **hierarchy of needs**:
1. **Business Goals** – high-level objectives such as revenue growth, market share, or user engagement.  
2. **Stakeholder Needs** – what employees need to fulfill business goals (e.g., access to timely data).  
3. **System Requirements** – the specifications the data system must satisfy to serve stakeholder needs.

System requirements divide into:
- **Functional requirements** describe *what* a system must do (e.g., fraud detection systems must report suspicious activity immediately).  
- **Non-functional requirements** describe *how well* the system must operate (e.g., latency, scalability, security).  

The process begins at the **top of the hierarchy**, ideally with conversations with executives like the CTO, ensuring alignment with corporate strategy. 

---

## Conversation with Matt Housley  
Matt Housley, co-author of *Fundamentals of Data Engineering*, highlights a key challenge in the field: most educational materials focus on **tools**, neglecting **mental frameworks**. His advice:  
- Develop **core data concepts** first (even with simple tools like Excel).  
- Build **broad competence** across technologies before specializing in a company’s stack.  
- Adopt a **framework-driven mindset** to classify tools and adapt to changing environments.  

The takeaway is that successful data engineers are not tool experts first, but **systems thinkers**.  

---

## Conversation with the CTO  
A mock conversation illustrates how business goals cascade into system requirements:  
- **Business challenges**: legacy technology risks, competitive pressures, and the need to expand internationally.  
- **Initiatives**: refactoring legacy code, scaling systems, adopting **streaming data** solutions, and building a **recommendation engine**.  
- **Implications for data engineers**:  
  - Collaborating with software teams to ensure analytics-ready schemas.  
  - Exploring AWS tools like **Kinesis** and **Kafka** for real-time data streaming.
  - Supporting ML workflows (e.g., powering a recommender system). 

This emphasizes the importance of bridging the **software–data divide** by aligning schema design and data processing needs.  

---

## Conversation with Marketing
Marketing stakeholders require **real-time insights** and **personalized recommendations**:
* Current dashboards show sales trends but with a two-day delay. Marketing needs near-real-time updates (e.g., hourly) to act on demand spikes with targeted promotions.
* Current recommender system is simplistic (“popular products of the week”). They need **personalized recommendations** that consider browsing history, purchase behavior, and cart contents.

The conversation confirms the importance of **timeliness** (data freshness) and **actionability** (ability to run campaigns). For data engineers, the functional requirement becomes:

* Deliver dashboards updated hourly.
* Build data pipelines to support a recommender system integrated with checkout flows.

---

## Breaking Down the Conversation with Marketing
Documenting requirements ensures clarity:
* **Business goals**: growth, retention, international expansion.
* **Stakeholder needs**: analytics dashboards + recommender system.
* **Functional requirements**:
  * Dashboards must serve data ≤ 1 hour old.
  * Recommender pipelines must provide training data, ingest real-time user/product data, and return recommendations.

Key lesson: *translate stakeholder needs into system-level requirements*. Dashboards are built by data scientists, but data engineers must ensure **data timeliness**. Similarly, engineers must deliver pipelines that allow models to be trained and deployed effectively.

---

## Conversation with the Software Engineer
Collaboration with source system owners is vital. Pain points include:
* Daily file exports are slow and risky for production systems.
* Schema changes break downstream scripts.
* Occasional outages create data unavailability.

Solutions proposed:
* **Read replica database** with an API for safer, continuous access.
* **Notifications** for outages or schema changes.
* **Consistency guarantees** in replicated databases to reduce instability.

This underscores the need for **communication and coordination** across teams to ensure pipelines remain robust and resilient.

---

## Documenting Nonfunctional Requirements
Non-functional requirements capture system qualities beyond raw functionality:

* **Dashboards**: must scale with user volume, ingest data with <1-hour latency, perform schema validation, and adapt to schema changes.
* **Recommender System**: must operate with <1 second latency, scale to 10k+ concurrent users, and have fallback behavior (e.g., defaulting to popular products if recommendations fail).

These ensure systems remain usable, reliable, and efficient under varying conditions.

---

## Requirements Gathering Summary
Core lessons:
* Always begin by understanding **business goals and stakeholder needs**.
* Conduct open-ended conversations to uncover pain points and desired actions.
* Document both functional and non-functional requirements for validation.
* Acknowledge **trade-offs**: scope, cost, and timeline form the “iron triangle” of project management. Optimizing all three simultaneously is a fallacy, but applying engineering principles (loose coupling, iterative design, stakeholder alignment) helps balance them effectively.

---

## Follow-up Conversation with the Data Scientist
The data scientist clarifies the **technical expectations** for the recommender:

* **Content-based model** using embeddings for users and products.
* Training data includes features (user demographics, product details) and ratings.
* Needs **batch pipelines** for retraining data and **streaming pipelines** for real-time recommendations.
* Latency requirement: ≈1 second round-trip for recommendations.
* Scalability: up to 10k concurrent users (and more in the future).

This adds precision to system requirements, making it possible to design concrete pipelines.

---

## Conversation Take-Aways
The project requires:
1. **Batch pipeline** – delivers training data for retraining models.
2. **Streaming pipeline** – serves real-time recommendations using embeddings.

Both pipelines must integrate with product data, user activity logs, and the recommendation model outputs.

---

## Details of the Recommender System
The recommender uses **embedding vectors**:
* **Product embeddings**: describe item features.
* **User embeddings**: capture user preferences.

Recommendations are made by calculating similarity between vectors. A **vector database** accelerates this process by storing embeddings and enabling fast nearest-neighbor searches.

Thus, the recommender system provides:
* **Profile-based recommendations**: “Based on your profile, you may like…”
* **Similarity-based recommendations**: “Because you viewed this item, you may like…”

---

## AWS Services for Batch Pipelines  
Batch pipelines on AWS commonly follow the **ETL pattern**:  
- **Ingestion**: Amazon RDS as a source.  
- **Transformation**:  
  - **AWS Lambda** (serverless, lightweight tasks).
  - **AWS Glue** (serverless ETL with crawlers and catalogs, convenience, metadata catalog, visual design).  
  - **Amazon EMR Serverless** (more control, flexibility, big data frameworks).  
- **Storage**:  
  - **Amazon S3** – cost-effective staging and integration.  
  - **Amazon Redshift** – complex analytics warehouse, higher cost.  
  - **RDS** - relational queries


The balance is between **control vs. convenience**. For ML training pipelines, **S3** is often the simplest and cheapest option for sharing data.

---

## AWS Services for Streaming Pipelines
Streaming workloads require real-time data flow:
* **Amazon Kinesis Data Streams** – simple, fully managed ingestion and processing.
* **Amazon MSK (Managed Streaming for Apache Kafka)** – full Kafka experience with more control.
* **Amazon Data Firehose** – simplified ingestion → storage pipelines (e.g., stream to S3/Redshift).

Kinesis is often recommended for beginners and lower operational overhead, while MSK suits teams already experienced with Kafka.

---

## AWS Services to Meet Your Requirements
Selecting the right AWS tools depends on functional and non-functional requirements:
* **Batch**: Glue ETL + S3 (convenience and ML training) or EMR (control at scale).
* **Streaming**: Kinesis for ease, MSK for flexibility, Data Firehose for simplified ingestion.

The right mix ensures both **scalability** and **operational efficiency**.
The principle is to avoid **undifferentiated heavy lifting**, selecting services that free engineers to focus on logic rather than infrastructure.  

---

## Lab Walkthrough - Implementing the Batch Pipeline
The lab ties everything together by:
1. Implementing the **batch pipeline** to deliver training data.
2. Setting up a **vector database** for embeddings.
3. Building the **streaming pipeline** to serve recommendations.

Through this exercise, learners interact with Terraform, AWS CLI, and core AWS services, reinforcing both the conceptual framework and hands-on practice.

---

### Conclusion
Stakeholder management and requirements gathering form the foundation of effective data engineering. By systematically engaging leadership, marketers, software engineers, and data scientists, data engineers can align system design with business objectives. Translating these needs into functional and non-functional requirements creates clarity, while AWS services provide the tools to implement scalable, reliable pipelines. Ultimately, success lies not just in building systems but in ensuring those systems deliver measurable business value.

---

## TL;DR
* Data engineering starts with **understanding stakeholders and business goals**.
* Requirements include both **functional (what systems do)** and **non-functional (how they perform)**.
* Conversations with CTOs, marketing, engineers, and data scientists ensure alignment.
* AWS offers powerful services for both **batch** (Glue, EMR, S3) and **streaming** (Kinesis, MSK, Firehose) pipelines.
* Clear documentation and thoughtful trade-off decisions are key to building sustainable data systems.

---

## Keywords / Tags
Data Engineering, Stakeholder Management, Requirements Gathering, Functional vs Non-functional Requirements, AWS Data Pipelines, ETL, Streaming Data, Kinesis, Glue, Recommender Systems

---

## SEO Meta-description
Learn stakeholder management and requirements gathering in data engineering, from business goals to AWS batch and streaming pipelines.

---

## Estimated Reading Time
**18–20 minutes**
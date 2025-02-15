# 📄 Introduction to Cloud Computing 
---
## 📋 **Overview**
Welcome to the "Introduction to Cloud Computing" workshop! In this session, we will explore the world of cloud computing and its applications. Cloud computing has revolutionized the way businesses and individuals store, manage, and process data. This workshop aims to provide you with a solid foundation in cloud computing concepts, services, and benefits. 

## 🎯 **Objectives**
By the end of this workshop, you will:

- Understand the fundamental concepts of cloud computing. 
- Learn about different cloud service models and deployment models.
- Explore popular cloud service providers such as AWS, GCP and Azure. 
- Gain hands-on experience with cloud resources and services such as AWS Amplify and AWS S3 Buckets.
- Understand the difference between IaaS and PaaS
- Understand the benefits and challenges of cloud adoption. 

## 🔍 **Prerequisites**
To participate in this workshop, you should have a basic understanding of computer systems. Please ensure you have the following requirements met:

- pythonanywhere Account
- AWS Account
- Credit Card Details to signup for AWS.

## 🚀 **Workshop Outline**

1. Pre - Cloud Era and its Difficulties
  ```mermaid
    graph LR
    A[Paying for Underutilized Resources] --> B[Host and Maintaining our own Servers]
    B --> C[Disaster Management and Availability]
    C --> D[Lack of MicroServices]
  ```
  - What are Micro services? Independent and Simple Cloud based tools which are integrated into your infrastructure.
  | Service | Description |
  |---|---|
  | AWS Lambda | Serverless compute service that automatically scales based on demand/traffic. |
  | AWS SES | Email sending service for marketing campaigns, transactional emails, or any other type of email. |
  | AWS IAM | Identity and Access Management service for controlling user access to AWS resources. It organizes users into roles and groups for easier management. |
  | AWS Secrets Manager | Secure storage service for sensitive information like passwords, API keys, and database credentials. |


2. Cloud Fundamentals
  ```mermaid
  graph LR
      A[What] --> B[How]
      B --> C[Why]
      C --> D[Impact]
  ```

3. Introduction to Cloud Computing
    - Overview of cloud computing and its importance: 
        - Cloud Computing is defined as the practice of using remote servers hosted on the internet to store, manage and process data rather than using a local. 
    - Benefits and challenges of adopting cloud services. 
    ```mermaid
    graph TB
    A[Cloud Computing] --> B[On-demand Network Access]
    A --> C[Resource Pooling]
    A --> D[Rapid Elasticity]
    A --> E[Measured Service]
    B --> F[Access Services Anytime]
    B --> G[Connectivity from Anywhere]
    C --> H[Shared Infrastructure]
    C --> I[Multi-tenancy]
    D --> J[Scale Resources Up or Down]
    D --> K[Pay for Actual Usage]
    E --> L[Monitor and Optimize Performance]
    E --> M[Pay for Actual Usage]
    ```

4. Cloud Service Models
    - Infrastructure as a Service (IaaS)
    - Platform as a Service (PaaS)
    - Software as a Service (SaaS)

        | Category | Service Model | Examples |
        | --- | --- | --- |
        | IAAS | Infrastructure as a Service | Amazon EC2, Azure Blob Storage, Google Cloud VPC |
        | SAAS | Software as a Service | Gmail, Google Docs, Salesforce |
        | PAAS | Platform as a Service | Heroku, Azure App Service, AWS RDS |
    

5. Cloud Deployment Models
    - Public, private, hybrid, and multi-cloud environments. 
    - Considerations for choosing a deployment model. 

    | Cloud Deployment Models | Considerations |
    | --- | --- |
    | Public Cloud | Scalability, Cost, Convenience |
    | Private Cloud | Control, Security, Compliance |
    | Hybrid Cloud | Flexibility, Data Sovereignty, Cost |
    | Multi-cloud | Vendor Lock-In, Redundancy, Data Portability |


6. Popular Cloud Service Providers
    - Amazon Web Services (AWS)
    - Google Cloud Platform (GCP) 
    - Microsoft Azure 
    ```mermaid
    graph LR
    E[Cloud Service Providers] --> A[AWS]
    E --> B[GCP]
    E --> C[Azure]
    ```

7. Cloud Services [AWS Amplify + AWS S3 Buckets]
    - Account setup on AWS.  
    - Hosting a website or app using AWS on Free Tier can be done in two ways: 

        | Service | Purpose|
        |---|---|
        | AWS Amplify | A service dedicated to hosting websites and applications on AWS Cloud, similar to Vercel and other website/app hosting services. |
        | AWS S3 Buckets | A service that provides scalable object storage containers in the cloud for data of any size and type. |
  <!--
     - AWS Amplify Visual Representation   
        ![](https://b.l3n.co/i/OPqaKo.png)

     - AWS S3 Bucket Visual Representation   
        ![](https://a.l3n.co/i/OPqxzP.png)
    --> 

8. Hands - On Lab
    - Lab - 1: 
      <iframe src="https://scribehow.com/embed/Deploy_Django_App_on_Cloud_using_pythonanywherecom__kzZar1_6Ti2jt0nZ2h5Wsw" width="100%" height="640" allowfullscreen frameborder="0"></iframe>
    - Lab - 2: 
      <iframe src="https://scribehow.com/embed/Create_AWS_Amplify_App_Deployment_for_Sivaab__rvt9hRXFRO2VZ4EjxU8jnA" width="100%" height="640" allowfullscreen frameborder="0"></iframe>
    - Lab - 3: 
      <iframe src="https://scribehow.com/embed/Hands__On_Lab2__AWS_S3_Bucket_for_Static_Website_Hosting__IuO7D6KTSuyRmtp269t8jQ" width="100%" height="640" allowfullscreen frameborder="0"></iframe>


10. Real-World Cloud Applications
    - Case studies and examples of cloud adoption. 
    - Industry-specific use cases. 

    | Cloud Applications | Case Studies and Examples | Industry-Specific Use Cases |
    | --- | --- | --- |
    | Infrastructure as a Service (IAAS) |  Netflix: Migrated its video streaming platform to AWS, leveraging its scalability and global reach. |  E-commerce: Hosting websites and managing scalable infrastructure for online retail. |
    | Software as a Service (SAAS) |  Salesforce: Provides customer relationship management (CRM) software as a cloud-based service. |  Healthcare: Managing electronic health records and telehealth solutions. |
    | Platform as a Service (PAAS) |  Heroku: Offers a cloud application platform for developers to deploy and scale applications. |  Financial Services: Building and deploying fintech applications for banking and investment management. |
    | Cloud Storage and Backup |  Dropbox: Provides cloud storage and file synchronization services for individuals and businesses. |  Media and Entertainment: Storing and streaming large media files for content distribution. |
    | Big Data and Analytics |  Airbnb: Utilizes cloud-based data analytics to gain insights into user behavior and optimize pricing. |  Manufacturing: Analyzing sensor data for predictive maintenance and optimizing production processes. |
    | Internet of Things (IoT) |  Philips Hue: Cloud-based smart lighting system enabling remote control and automation. |  Smart Cities: Collecting and analyzing data from connected devices to improve urban infrastructure. |


11. Future Trends in Cloud Computing
    - Serverless computing
    - Edge computing
    - Artificial Intelligence (AI) and Machine Learning (ML) in the cloud 
    ```mermaid
    graph LR
    A[Future Trends] --> B[Serverless Computing]
    A --> C[Edge Computing]
    A --> D[AI and ML in the Cloud]

    B --> B1[Automatic Scaling]
    B --> B2[Cost Optimization]
    B --> B3[Event-driven Execution]

    C --> C1[Reduced Latency]
    C --> C2[Real-time Processing]
    C --> C3[Beneficial for IoT and Data-intensive Workloads]

    D --> D1[Scalable Infrastructure]
    D --> D2[Development, Training, and Deployment of AI/ML Models]
    D --> D3[Pre-built AI Services]
    ```


## 🌐 **Additional Resources**
To continue your learning journey beyond this workshop, here are some recommended resources:

1. Books:
    - "Cloud Computing: Concepts, Technology & Architecture" by Thomas Erl, Ricardo Puttini, and Zaigham Mahmood 📚
    - "Cloud Native: Using Containers, Functions, and Data to Build Next-Generation Applications" by Boris Scholl, Trent Swanson, and Peter Jausovec 📚

2. Online Courses:
    - Coursera: "Cloud Computing Basics" by University of Illinois at Urbana-Champaign 🖥️
    - FreeCodeCamp : "AWS Certified Cloud Practitioner Training 2020" by Andrew Brown 🎓

---

 *To make such stunning visual documentation you can refer to the [MarkDown Tutorial](https://ahmedthahir.github.io/gdscbpdc/2022-2023/02_Markdown/) by GDSC!*

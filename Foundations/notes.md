# Foundations — Roles and Concepts

## 1. Data Discovery

Before building any analytics system, several foundational questions must be answered:

1. What data are we going to work with, and why?
    
2. Who owns the data, and where is it located?
    
3. What transformations will be applied to the data?
    
4. Who is the target audience (data consumers)?
    
5. What systems will consume the final data?
    

These questions are addressed through the **Data Discovery process**.

---

## 2. Data Discovery Steps

1. **Identify Business Value**  
    Perform a _business-value analysis_ to determine why the data matters.
    
2. **Identify Data Consumers**  
    Define who will use the data and for what purposes.
    
3. **Identify Data Sources & Operating Modes**  
    Determine where data originates and how it is generated (batch, streaming, APIs, etc.).
    
4. **Define Data Management Approach**  
    Establish governance around:
    
    - Storage
        
    - Cataloging
        
    - Access control / permissions
        
5. **Define Processing Mechanisms**  
    Design how data will be processed, transformed, and operationalized.
    

---

## 3. AWS Modern Data Architecture

A **modern data architecture** aims to eliminate data silos by integrating disparate datasets into a unified, governed ecosystem that enables organization-wide data access and usage.

### Core Principles

- Eliminate isolated data silos
    
- Enable centralized governance
    
- Provide end-to-end data accessibility
    

---

### Basic Building Blocks

1. **Ingest**  
    Collect data from multiple sources and formats into the system.
    
2. **Store**  
    Centralize data into a unified repository instead of isolated departmental systems.
    
3. **Catalog**  
    Index and organize data for discoverability, searchability, and governance.
    
4. **Process**  
    Transform raw data into structured, usable, and analytics-ready formats.
    
5. **Deliver**  
    Provide processed data to consumers according to defined business rules and access policies.
    

---

## 4. AWS Services by Data Architecture Stage

### 4.1 Storage (Data Lake Layer)

- **Amazon S3 (Simple Storage Service)**  
    Core centralized storage for structured, semi-structured, and unstructured data.
    

---

### 4.2 Data Ingestion & Movement

- **AWS Database Migration Service (DMS)** — relational and non-relational database migration
    
- **Amazon Data Firehose** — streaming data ingestion and delivery
    
- **Amazon Managed Streaming for Apache Kafka (MSK)** — managed Kafka clusters
    
- **AWS IoT Core** — ingestion and routing of IoT device data at scale
    
- **AWS DataSync** — high-speed data transfer from on-premises systems
    
- **AWS Transfer Family** — managed file transfers (SFTP, FTPS, etc.) into S3
    
- **AWS Snowball** — physical data transfer devices for large-scale or low-network environments
    

---

### 4.3 Data Cataloging

- **AWS Glue Data Catalog**  
    Central metadata repository enabling data discovery, schema management, and indexing.
    

---

### 4.4 Data Processing

- **AWS Glue** — serverless ETL service
    
- **Amazon EMR** — distributed processing using frameworks like Spark, Hadoop, etc.
    
- **Amazon Managed Service for Apache Flink** — real-time stream processing
    

---

### 4.5 Data Analytics & Consumption

- **Amazon Redshift** — data warehouse for analytics
    
- **Amazon Athena** — SQL queries directly on S3
    
- **Amazon EMR** — large-scale data processing and analytics
    
- **Amazon OpenSearch Service** — search and log analytics
    
- **Amazon QuickSight** — business intelligence and visualization
    
- **Amazon SageMaker** — machine learning model development and deployment
    

---

### 4.6 Governance, Security & Compliance

- **AWS Lake Formation** — data lake security and governance
    
- **AWS Identity and Access Management (IAM)** — access control and permissions
    
- **AWS Key Management Service (KMS)** — encryption key management
    
- **Amazon Macie** — sensitive data discovery and classification
    
- **Amazon DataZone** — data cataloging and governance for enterprise data sharing
    
- **AWS Audit Manager** — continuous audit readiness and compliance tracking
    

---
### AWS Security Services

The following is a partial list of AWS services used for security.  
These services can be used across multiple security categories.

---

#### Access Management

- **AWS IAM (Identity and Access Management)**  
    Manages fine-grained access and permissions for:
    
    - Human users
        
    - Software users
        
    - AWS services
        
    - Microservices
        
- **AWS Certificate Manager (ACM)**  
    Used to provision, manage, and deploy **SSL/TLS certificates** for AWS services and applications.
    

---

#### Regulatory Compliance

- **AWS Audit Manager**  
    Automatically collects and organizes evidence from AWS services and converts it into auditor-friendly reports for compliance standards such as:
    
    - GDPR
        
    - PCI DSS
        
    - and others
        
- **AWS Config**  
    Provides configuration management and auditing of AWS resources to assess:
    
    - Security posture
        
    - Compliance posture over time
        

---

#### Sensitive Data Protection

- **Amazon Macie**  
    Uses **Machine Learning (ML)** and pattern matching to discover and protect sensitive data such as:
    
    - Personally Identifiable Information (PII)
        
- **AWS Key Management Service (KMS)**  
    Used to encrypt and decrypt data:
    
    - At rest
        
    - In transit
        
    
    Supports:
    
    - Customer-managed keys
        
    - AWS-managed keys
        
- **AWS Glue**  
    Protects sensitive data using:
    
    - Data encryption with AWS KMS
        
    - Data masking
        

---

#### Data and Network Security

- **AWS Control Tower**  
    Helps set up and operate a secure **multi-account AWS environment** using prescriptive controls.
    
- **Amazon GuardDuty**  
    Threat detection service that identifies potential security issues by monitoring:
    
    - Networks
        
    - Applications
        
    - User activity
        
    - AWS resources
        
- **AWS WAF (Web Application Firewall)**  
    Protects web applications from:
    
    - Common exploits
        
    - Application attacks
        
    - Availability threats
        
- **AWS Shield**  
    Provides **DDoS (Distributed Denial of Service)** protection against volumetric attacks.
    

---

#### Data Auditability

- **AWS CloudTrail**  
    Provides auditing and logging of:
    
    - API calls
        
    - Management events
        
    
    Used for:
    
    - Security monitoring
        
    - Compliance tracking
        
- **AWS Lake Formation**  
    Automatically catalogs:
    
    - Source of data
        
    - Destination of data
        
    
    Stores metadata in **AWS Glue Data Catalog**, including:
    
    - Origin
        
    - Landing location
        
    - Transformations
        
- **AWS Glue Data Catalog**  
    Tracks metadata changes as data moves between services like:
    
    - Amazon S3
        
    - Amazon Redshift
        
    - and others
        
    
    This helps trace the full data flow.
    

---

### Security Best Practices

AWS recommends the following best practices for securing data analytics pipelines:
#### 1. Implement Robust Access Control

- Create IAM roles and policies
    
- Control who can access which resources
    

---
#### 2. Encrypt Data at Rest and In Transit

- Use **AWS KMS** for encryption at rest
    
- Use **HTTPS/TLS** for encryption in transit between services
    

---
#### 3. Use Data Masking

Apply masking and anonymization techniques to protect sensitive data such as:

- PII
    

while still allowing analytics operations.

---
#### 4. Use Network Isolation Techniques

Use:

- VPC (Virtual Private Cloud)
    
- Network ACLs (Access Control Lists)
    

to avoid exposing resources publicly.

---
#### 5. Understand Applicable Laws

Follow:

- Industry regulations
    
- Geographic compliance laws
    

and ensure the architecture conforms to them.

---
#### 6. Classify Data

Create data classes based on sensitivity and apply appropriate security controls for each class.

---
#### 7. Plan for Disaster Recovery

Implement:

- Backup procedures
    
- Recovery plans
    
- High availability
    
- Redundancy
    

to ensure continuity of operations.

---
#### 8. Define and Implement Data Governance

Design:

- Flexible
    
- Comprehensive
    
- Robust governance policies
    

for long-term data management.

---

### Monitoring

Monitoring is critical for maintaining:

- Reliability
    
- Availability
    
- Performance
    

of AWS data analytics workflows.

---
### What Should Be Monitored

#### 1. Resources

Monitor AWS resources such as:

- EC2 instances
    
- Databases
    
- Data stores
    

Important metrics include:

- CPU utilization
    
- Memory usage
    
- Network traffic
    
- Disk I/O
    

These help identify performance bottlenecks.

---
#### 2. Analytics Jobs

Monitor ETL / ELT jobs using metrics such as:

- Job runtime
    
- Errors encountered
    
- Records processed
    

This helps evaluate performance and troubleshoot failures.

---
#### 3. Data Pipelines

Services like:

- AWS Glue
    
- AWS Step Functions
    
- AWS Lambda
    

are commonly used to orchestrate workflows and should be monitored for:

- Pipeline health
    
- Failures
    
- Bottlenecks
    

---
#### 4. Data Access

Track:

- Permissions
    
- Access logs
    

using:

- IAM
    
- CloudTrail
    

to maintain:

- Security
    
- Governance
    

---
### AWS Monitoring Services

#### Amazon CloudWatch

Collects metrics from:

- EC2
    
- Databases
    
- Data pipelines
    

Used for:

- Alarms
    
- Dashboards
    
- Performance visualization
    

---
#### AWS CloudTrail

Provides visibility into:

- API calls
    
- User activity
    

Useful for:

- Security monitoring
    
- Access troubleshooting
    

---
#### AWS X-Ray

Provides:

- End-to-end monitoring
    
- Performance insights
    

for applications and their underlying AWS services.

---
#### Amazon GuardDuty

Detects:

- Malicious behavior
    
- Unauthorized activities
    

in workloads and AWS environments.

---
#### AWS Systems Manager

Provides:

- Application-level monitoring for EC2
    

and helps automate operational tasks.

---

### Monitoring Best Practices

#### 1. Test and Validate Analytics Jobs

Test deployments before production changes to ensure:

- Performance
    
- Accuracy
    
- Stability
    

---

#### 2. Monitor Key Metrics at Each Stage

Examples include:

- ETL success/failure rates
    
- Model training times
    
- Number of predictions made
    

This improves troubleshooting and optimization.

---
#### 3. Set Up Alerts for Critical Failures

Notify the responsible teams immediately to reduce downtime and speed up issue resolution.

---

#### 4. Integrate Monitoring with Visualization Tools

Use tools like:

- Amazon Managed Grafana
    
- Amazon QuickSight
    

to create dashboards for end-to-end workflow visibility.

---

#### 5. Periodically Review Metrics

Review usage patterns regularly to:

- Identify inefficiencies
    
- Improve performance
    
- Optimize costs

---

*Certificate of completion: [View](assets/certificate.pdf)*
# Day 23 - Amazon S3 (Simple Storage Service)

## What I Learned
- Amazon S3 is a cloud storage service provided by AWS
- S3 stands for Simple Storage Service
- It is used to store and retrieve data from anywhere on the internet
- S3 provides scalable, secure, and durable object storage
- It is widely used for backups, static websites, media storage, and data lakes

## What is Amazon S3
- Amazon S3 is an object storage service in AWS
- Data is stored as objects inside buckets
- It can store files like images, videos, documents, logs, and backups
- S3 is highly scalable and supports virtually unlimited storage

Amazon S3 is an object storage service that offers scalability, security, availability, and high performance.

## Key Concepts in S3

### Bucket
- A bucket is a container used to store objects
- Each bucket has a globally unique name

### Object
- Files stored in S3 are called objects
- Each object contains:
  - Data
  - Metadata
  - Unique identifier (key)

### Key
- A key is the unique name of an object inside a bucket

## Features of Amazon S3
- Unlimited storage capacity
- High durability and availability
- Secure data storage
- Easy access through internet
- Supports backup and disaster recovery

Amazon S3 provides secure and highly durable cloud storage for different use cases such as backups, applications, and analytics.

## Storage Classes in S3

### S3 Standard
- Used for frequently accessed data

### S3 Intelligent-Tiering
- Automatically moves data to cost-effective tiers

### S3 Glacier
- Used for long-term archive storage

### S3 Glacier Deep Archive
- Lowest-cost storage for rarely accessed data

## Common Use Cases
- Website hosting
- Media file storage
- Application backups
- Log storage
- Big data analytics

## Advantages of S3
- Scalable cloud storage
- Cost-effective pricing
- High security
- Easy integration with AWS services
- Reliable backup solution

## Real Use Case
A company stores user-uploaded images in Amazon S3:
- Images are uploaded into S3 buckets
- Applications access images through URLs
- Backup and recovery become easier

This reduces the need for physical storage infrastructure.

## Basic AWS CLI Commands

### Create Bucket
```bash
aws s3 mb s3://my-bucket
```
### List Buckets
```bash
aws s3 ls
```
### Upload File
```bash
aws s3 cp file.txt s3://my-bucket
```
### Download File
```bash
aws s3 cp s3://my-bucket/file.txt .
```

### Summary
Amazon S3 is a scalable and secure cloud object storage service provided by AWS. It is widely used for storing files, backups, media content, and application data with high durability and availability. 

### My Learning Reflection
Today I learned how Amazon S3 works and how data is stored using buckets and objects. I understood its importance in cloud storage, backup systems, and modern DevOps infrastructure.

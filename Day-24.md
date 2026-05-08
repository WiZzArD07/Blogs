# Day 24 - AWS IAM (Identity and Access Management)

## What I Learned
- AWS IAM is a security service used to manage access to AWS resources
- IAM stands for Identity and Access Management
- It controls who can access AWS services and what actions they can perform
- IAM helps implement secure authentication and authorization
- It follows the principle of least privilege for better security

## What is AWS IAM
- AWS IAM is a web service that securely controls access to AWS resources
- It allows administrators to create users, groups, roles, and policies
- IAM ensures only authorized users and services can access resources

AWS IAM securely manages access to AWS services and resources using authentication and authorization mechanisms.

## Why IAM is Important
- Prevents unauthorized access
- Provides secure user management
- Enables fine-grained permissions
- Supports multi-factor authentication (MFA)
- Improves cloud security

## Core Components of IAM

### IAM User
- Represents a person or application using AWS
- Has credentials like password or access keys

### IAM Group
- Collection of IAM users
- Permissions can be assigned to groups

### IAM Role
- Temporary identity with specific permissions
- Commonly used by AWS services and applications

### IAM Policy
- JSON document defining permissions
- Specifies allowed or denied actions

IAM policies define what actions users, groups, or roles can perform on AWS resources.

## Types of IAM Policies

### Managed Policies
- Predefined policies created by AWS or users

### Inline Policies
- Policies directly attached to a user, group, or role

## Example IAM Policy
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Resource": "*"
    }
  ]
}
```
### IAM Best Practices
 - Never use root account for daily tasks
 - Enable Multi-Factor Authentication (MFA)
 - Grant minimum required permissions
 - Rotate access keys regularly
 - Use IAM roles instead of sharing credentials
AWS recommends using least privilege access and MFA for improving account security.

### Common Use Cases
 - Managing developer access
 - Securing AWS resources
 - Providing temporary permissions
 - Controlling application access

### Advantages of IAM
 - Centralized access management
 - Enhanced cloud security
 - Fine-grained permission control
 - Supports temporary credentials
 - Easy integration with AWS services

### Real Use Case
A company has multiple employees:
 - Developers need EC2 access
 - Database team needs RDS access
 - Admin team requires full control

Using IAM:
 - Separate roles and policies are created
 - Each team gets only required permissions
 - Security and management become easier

### Summary
AWS IAM is a core security service that controls authentication and authorization in AWS. It allows secure management of users, groups, roles, and permissions while protecting cloud resources from unauthorized access.

### My Learning Reflection
Today I learned how AWS IAM works and why it is important for cloud security. I understood concepts like users, groups, roles, and policies which are essential for managing permissions in AWS environments.
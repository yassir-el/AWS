**( Remember The best way to learn is to dirty your hands )**

# What is IAM?

IAM stands for Identity and Access Management. It is a web service that helps you securely control access to AWS resources. You use IAM to control who can use your AWS resources (authentication) and what resources they can use and in what ways (authorization).

# How IAM works?

* Users: A user is an entity that you create in AWS. It can be a person, a system, or an application that needs to interact with AWS resources.
* Groups: A group is a collection of users. Instead of attaching policies to users one by one, you can create groups, attach policies to the groups, and then add users to the groups.
* Roles: A role is an entity that defines a set of permissions for making AWS service requests. IAM roles are not associated with a specific user or group. Instead, trusted entities assume roles, such as IAM users, applications, or AWS services such as EC2.

# IAM Policy Simulator




QUESTION 6

Which is the best way to enable S3 read-access for an EC2 instance?


Configure a bucket policy which grants read-access based on the EC2 instance name


Create a new IAM group and grant read access to S3. Store the group's credentials locally on the EC2 instance and configure your application to supply the credentials with each API request.


Create an IAM role with read-access to S3 and assign the role to the EC2 instance


Create a new IAM role and grant read-access to S3. Store the role's credentials locally on the EC2 instance and configure your application to supply the credentials with each API request

Good work!
Correct. IAM roles allow applications to securely make API requests from instances, without requiring you to manage the security credentials that the applications use.



QUESTION 7

Which of the following statements is NOT true?


AWS recommends IAM roles so that your applications can securely make API requests from your instances.


AWS offers EC2 Instance Connect, a convenient and robust solution for establishing connections to Linux instances through Secure Shell (SSH).


Control access to Amazon EC2 resources by setting up security groups.


AWS recommends that EC2 instances have credentials stored on them so that the instances can access other resources (such as S3 buckets).

Sorry!
AWS recommends IAM roles so that your applications can securely make API requests from your instances, without requiring you to manage the security credentials that the applications use.

Correct Answer
You can hard-code AWS access keys into your application or instances, but you’re faced with the added responsibility of distributing them to the instance securely and then the management headache of regularly rotating them. AWS doesn't recommend this practice.
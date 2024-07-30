
HANDS-ON LAB Configure and Work with CodeCommit from the CLI

CodeDeploy Lifecycle Event Hooks

HANDS-ON LAB Deploying an Application Using CodeDeploy

CodePipeline 101

CodePipeline Demo - Part 1

CodePipeline Demo - Part 2

HANDS-ON LAB Setting Up an AWS CodePipeline with a Manual Approval

Introducing CodeArtifact

Demo - Creating a CodeArtifact Repository

Elastic Container Service

Introduction To CloudFormation

Provisioning Resources Using CloudFormation Demo

HANDS-ON LAB Create a DynamoDB Table Using CloudFormation

Exporting CloudFormation Stack Values

The Serverless Application Model (SAM)

CloudFormation and SAM Demo

CloudFormation Nested Stacks

HANDS-ON LAB Working with CloudFormation Nested Stacks

Introducing The Cloud Development Kit (CDK)

CDK Demo

Introducing Amplify

Amplify Demo

Developer Theory Summary - Part 1

Developer Theory Summary - Part 2

QUIZ AWS Certified Developer - Associate - Developer Theory Quiz




# What is CI/CD

CI/CD stands for Continuous Integration and Continuous Deployment. 

Continuous Integration is the practice of automatically building and testing code changes as they are committed to the source code repository.

Continuous Deployment is the practice of automatically deploying code changes to a staging or production environment.

# CodeCommit 101

AWS CodeCommit is a fully-managed source control service that makes it easy for teams to host secure and highly scalable private Git repositories.

# CodeDeploy 101

AWS CodeDeploy is a fully-managed deployment service that automates software deployments to a variety of compute services such as Amazon EC2, AWS Fargate, AWS Lambda, and your on-premises servers.

## The CodeDeploy Types

- In-place deployments: The application on the instance is stopped, the new version is installed, and the application is restarted.
- Blue/green deployments: The new version of the application is deployed alongside the old version. Traffic is then switched from the old version to the new version.

## in-place vs blue/green deployments

- In-place deployments are faster and require less infrastructure.
- Blue/green deployments are safer and allow for zero-downtime deployments.

- In-place: 
    Capacity is reduced during deployment
    Rollback is more difficult
    Faster

- Blue/green:
    No capacity reduction
    Rollback is easy
    Safer

# The CodeDeploy AppSpec File

The AppSpec file is a YAML-formatted file used by AWS CodeDeploy to manage a deployment. It defines the deployment actions, such as which files to copy to the instance, which scripts to run, and which services to restart.

## AppSpec File Structure

- version: The version number of the AppSpec file format.
- os: The operating system of the instance.
- files: The list of files to copy to the instance.
- hooks: The lifecycle event hooks to run during the deployment.

## AppSpec File Example

```yaml
version: 0.0
os: linux
files:
  - source: /
    destination: /var/www/html
hooks:
    BeforeInstall:
        - location: scripts/install_dependencies.sh
        timeout: 300
        runas: root
    AfterInstall:
        - location: scripts/start_server.sh
        timeout: 300
        runas: root
```

## AppSpec Folder Structure

- appspec.yml: The main AppSpec file.
- scripts: The folder containing the scripts to run during the deployment.
- config: The folder containing the configuration files to copy to the instance.
- source: The folder containing the application files to copy to the instance.

# CodeDeploy Lifecycle Event Hooks


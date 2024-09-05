### AWS EKS

Till that moment we used k8s in docker desktop (and we will continue using it for development purposes). In addition to
that, we will need to create EKS cluster (like a production).
Amazon Elastic Kubernetes Service (Amazon EKS) is a managed Kubernetes service that makes it easy for you to run
Kubernetes on AWS and on-premises.

### Sub Task1 (Manual creation of all AWS resources)

An aim of this task is to get familiar with AWS resources which are needed for EKS cluster creation.
As a result of this task we expect below:

1. Create VPC.
2. Create Security Zones.
3. Create node groups needed for EKS cluster.
4. Create EKS clusters in the VPC.
5. Deploy all 3rd party helm charts.
6. Deploy news-aggregator and news-aggregator operator.

### Sub Task2 (CDK)

The AWS Cloud Development Kit (AWS CDK) is an open-source software development framework for defining cloud
infrastructure in code and provisioning it through AWS CloudFormation.

In the scope of this task, you need to automate the infrastructure creation using CDK. CDK should deploy all resources
needed by EKS cluster (from sub task #1).

### Useful links

* [EKS](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html)
* [CDK](https://docs.aws.amazon.com/cdk/v2/guide/home.html)
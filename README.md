# Introduction

This repository was built to support the meetup "AWS Hosting Strategy" on AWS User Group placed at BJSS Lisbon office on Aug, 24th, 2023.

# Overview

## Source code

The Vue.js source code used in this project can be found here https://github.com/renatomatos79/bjss-aws-demo/tree/main/src/todo-vue

## Creating a free domain and using AWS Route 53 Hosted Zone

In this section we are gonna learn how to:

- Create a free domain
- Move it to AWS DNS Zone
- Build a free SSL certificate

https://github.com/renatomatos79/bjss-aws-demo/tree/main/services/0.route%2053

## Hosting a Vue.js projet using: 

### S3 Bucket

This section we have three short animations showing us how to deploy our Vue.js application using a S3 Bucket 

[Link to the folder](https://github.com/renatomatos79/bjss-aws-demo/tree/main/services/1.s3-bucket)

### Cloudfront

This section contains one animation showing us how to use Cloudfront to deploy our Vue.js application using a S3 Bucket using a custom subdomain 

[Link to the folder](https://github.com/renatomatos79/bjss-aws-demo/tree/main/services/2.cloudfront)

### Amplify

This section contains three nice animations helping us to easy deploy our Vue.js project

[Link to the folder](https://github.com/renatomatos79/bjss-aws-demo/tree/main/services/3.amplify)

### EC2

This is very detailed section that contains four nice videos showing us:

- How to use the compute capacity to build an EC2 Ubuntu instance
- Use SSH to connect to this instance
- Setup nodejs, docker, and git
- Build our project and docker image
- Run our docker image
- Access our Vue.js project using a public IP

[Link to the folder](https://github.com/renatomatos79/bjss-aws-demo/tree/main/services/4.ec2)

### Elastic Beanstalk

This section contains two videos showing us how to use Elastic Beanstalk to host our Vue.js docker project in a very simple way.

[Link to the folder](https://github.com/renatomatos79/bjss-aws-demo/tree/main/services/5.beanstalk)

### ECS (Amazon Elastic Container Service)

Amazon Elastic Container Service is a feature that runs highly secure, reliable, and scalable containers.
In this section using three very detailed videos we are gonna learn how to:
- Create and send our Vue.js docker image to Amazon Elastic Container Registry
- Create an ECS Cluster
- Define a task definition for our image
- Create a service and scale it to run our task definition

[Link to the folder](https://github.com/renatomatos79/bjss-aws-demo/tree/main/services/6.ecs)

### EKS (Amazon Elastic Kubernetes Service)

Amazon Elastic Kubernetes Service is the most trusted way to start, run, and scale Kubernetes services.
This section contains four great videos showing us how to:
- Connect to our EC2 instance and install awscli, kubectl, terraform
- Provision our EKS Cluster using terraform
- Connect to the EKS Cluster
- Deploy our Vue.js docker container to EKS Cluster
- Resolve the grant access issue in order to allow our AWS Account to inspect the EKS Cluster

[Link to the folder](https://github.com/renatomatos79/bjss-aws-demo/tree/main/services/7.eks) 

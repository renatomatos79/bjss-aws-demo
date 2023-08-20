# bjss-aws-demo.

Credentials used to "aws configure" were placed in C:\Users\renato.matos\Desktop\Project\aws folder

# S3 Bucket without CDF

http://bjss-aws-no-cdf.s3-website-us-east-1.amazonaws.com/

# S3 Bucket with CDF and Domain name

https://cdf.bjss-aws.pt/

# Amplify

https://amplify.bjss-aws.pt

# ECS - Elastic Container Service

registry: public registry bjss-aws
ecs-bjss-aws-cluster
ecs-bjss-aws-task-definition
ecs-bjss-aws-task
ecs-bjss-aws-service

Attention!
To stop a task, just click on the service, identify the task and click on stop
But don't forget to update the service and set the "Desired tasks" field to be zero, otherwise, another task will be auto recreated

Attention!
Select the task, and then inspect the public IP in order to access the URL for your app

# AWS EC2 access

=> Accessing EC2
ssh -i "C:\Users\renato.matos\.ssh\bjss-aws.pem" ubuntu@ec2-3-91-155-96.compute-1.amazonaws.com

=> Setup docker
sudo apt -y update
sudo apt -y upgrade
sudo apt -y install docker.io
sudo systemctl enable --now docker
docker --version
sudo usermod -aG docker ubuntu
docker run hello-world

=> Running container
docker run -d --name todoapp-latest -p 80:80 public.ecr.aws/g8g7h5m7/bjss-aws:latest

=> Accessing Todo website (Go to EC2 and check the Public Newtowk Address)
http://18.207.195.18/

=> Accessing Todo website using subdomain "todo-ec2" over Route 53 (Must route to the Private Network IP)
http://ec2.bjss-aws.pt/

# AWS EBT (Elastic Beanstalk)

Before start:
we must create this role name:

- aws-elasticbeanstalk-ec2-role

And apply these policies:

- AWSElasticBeanstalkWebTier
- AWSElasticBeanstalkWorkerTier
- AWSElasticBeanstalkMulticontainerDocker

After that, let's create our Beanstalk app

app name: ebt-bjss-aws
env: demo
domain: bjss-aws-ebt
platform: Docker
Single instance (free tier eligible)
service role: aws-elasticbeanstalk-ec2-role
Instance settings: Enabled Public IP
Network: us-east-1a, us-east-1b

As a result, Elastic Beanstalk created a named EC2 instance "demo" for us

To update your Docker application, you just need to create a zip file that contains the Dockerfile and the dist folder
Check the file name C:\tmp\bjss-aws-demo\beanstalk\beanstalk-docker.zip

How to access our app using a temp domain:
http://bjss-aws-ebt.us-east-1.elasticbeanstalk.com/

Go to the Route 53 and add an alias for your beanstalk app (bjss-aws-ebt.us-east-1.elasticbeanstalk)

https://beanstalk.bjss-aws.pt

# Docker Playground

https://github.com/renatomatos79/playground/tree/master/lesson-004

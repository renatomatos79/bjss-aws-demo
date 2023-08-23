# Before start

we must create this role name:

- aws-elasticbeanstalk-ec2-role

And apply these policies:

- AWSElasticBeanstalkWebTier
- AWSElasticBeanstalkWorkerTier
- AWSElasticBeanstalkMulticontainerDocker

# AWS EBT (Elastic Beanstalk)

After that, let's create our Beanstalk app

app name: ebt-bjss-aws
env: demo
domain: ebt-bjss-aws
platform: Docker
Single instance (free tier eligible)
service role: aws-elasticbeanstalk-ec2-role
Instance settings: Enabled Public IP
Network: us-east-1a, us-east-1b

As a result, Elastic Beanstalk created a named EC2 instance "demo" for us

# Updating the application

To update your Docker application, you just need to create a zip file that contains the Dockerfile and the dist folder
Check the file name bjss-aws-demo\beanstalk\beanstalk-docker.zip

# How to access our app using a temp domain:

http://bjss-aws-ebt.us-east-1.elasticbeanstalk.com/

Go to the Route 53 and add an alias for your beanstalk app (bjss-aws-ebt.us-east-1.elasticbeanstalk)

https://beanstalk.bjss-aws.pt

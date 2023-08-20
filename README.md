# bjss-aws-demo.

# S3 Bucket without CDF

http://bjss-aws-no-cdf.s3-website-us-east-1.amazonaws.com/

# S3 Bucket with CDF and Domain name

https://cdf.bjss-aws.pt/

# AWS Ec2 access

=> Setup docker
sudo apt -y update
sudo apt -y upgrade
sudo apt -y install docker.io
sudo systemctl enable --now docker
docker --version
sudo usermod -aG docker ubuntu
docker run hello-world

=> Running container
docker run -d --name todoapp-1.0.1 -p 80:80 renatomatos79/bjss:todo-1.0.1

=> Accessing EC2
ssh -i "C:\Users\renato.matos\.ssh\bjss-aws.pem" ubuntu@ec2-3-82-136-140.compute-1.amazonaws.com

=> Accessing Todo website
http://18.207.195.18/

=> Accessing Todo website using subdomain "todo-ec2" over Route 53
http://ec2.bjss-aws.pt/

# ECS - Elastic Container Service

registry: public registry bjss-aws
ecs-bjss-aws-cluster
ecs-bjss-aws-task
ecs-bjss-aws-service

# Docker Playground

https://github.com/renatomatos79/playground/tree/master/lesson-004

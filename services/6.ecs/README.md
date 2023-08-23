# ECS - Elastic Container Service

registry: public registry bjss-aws
ecs-bjss-aws-cluster
ecs-bjss-aws-task-definition
ecs-bjss-aws-task
ecs-bjss-aws-service

image name: bjss-aws:latest
image url: public.ecr.aws/g8g7h5m7/bjss-aws:latest

Attention!
To stop a task, just click on the service, identify the task and click on stop
But don't forget to update the service and set the "Desired tasks" field to be zero, otherwise, another task will be auto recreated

Attention!
Select the task, and then inspect the public IP in order to access the URL for your app

## Getting Started connecting to our EC2 instance

```bash
ssh -i "C:\Users\renato.matos\.ssh\bjss-aws.pem" ubuntu@ec2-3-84-141-243.compute-1.amazonaws.com
```

### Tagging and publishing to aws

Don't forget to access your EC2 instance and run the command below to connect to the Container Registry

```bash
aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/g8g7h5m7
cd bjss-aws-demo/src/todo-vue/
docker image build -t bjss-aws:latest .
docker tag bjss-aws:latest public.ecr.aws/g8g7h5m7/bjss-aws:latest
docker push public.ecr.aws/g8g7h5m7/bjss-aws:latest
docker run -d --name todoapp-latest -p 80:80 public.ecr.aws/g8g7h5m7/bjss-aws:latest
```

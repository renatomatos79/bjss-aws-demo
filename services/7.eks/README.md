# Connecting to the EC2 instance

```bash
ssh -i "C:\Users\renato.matos\.ssh\bjss-aws.pem" ubuntu@ec2-34-235-147-244.compute-1.amazonaws.com

```

# Install awscli

```bash
sudo yum remove awscli
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
sudo apt install zip
unzip awscliv2.zip
sudo ./aws/install
aws --version
```

# Installing kubectl

```bash
export K8S_RELEASE=1.27.0
curl -LO https://dl.k8s.io/release/v$K8S_RELEASE/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
kubectl version --short
```

# Installing terraform

## Install gnupg

```bash
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
```

## Install the HashiCorp

```bash
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg

```

## Add the official HashiCorp repository to your system

```bash
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list

```

## System update

```bash
sudo apt update

```

## Install Terraform

```bash
sudo apt-get install terraform
terraform --version

```

- https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli

# Setup AWS Account

```bash
aws configure
AWS Access Key ID [****************2DW5]: type your access key
AWS Secret Access Key [****************rRF4]: type your secret
Default region name [us-east-1]: us-east-1
Default output format [None]:

```

# Clone our GitHub repository

```bash
Git clone git@github.com:renatomatos79/bjss-aws-demo.git
cd bjss-aws-demo/services/7.eks/terraform
terraform init
terraform apply
```

# Connecting to the cluster

```bash
aws eks --region us-east-1 update-kubeconfig --name eks-bjss-demo
kubectl get nodes

```

# Deploying the todo-mvc application

```bash
cd ~/bjss-aws-demo/src/todo-vue
kubectl apply -f k8s.yaml
```

# Giving admin access to the cluster

```bash
cd ~/bjss-aws-demo/eks/roles
kubectl apply -f eks-map-admin-user.yaml
```

At this moment connect to the cluster using your AWS Admin Cluster Account

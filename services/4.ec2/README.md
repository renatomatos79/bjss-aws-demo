## Getting Started.

```bash
ssh -i "C:\Users\renato.matos\.ssh\bjss-aws.pem" ubuntu@ec2-18-215-244-189.compute-1.amazonaws.com
```

## Installing docker

```bash
sudo apt -y update
sudo apt -y upgrade
sudo apt -y install docker.io
sudo systemctl enable --now docker
docker --version
sudo usermod -aG docker ubuntu
docker run hello-world
```

## Installing nodejs

```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - &&\
sudo apt-get install -y nodejs
node --version
npm --version
```

## Installing git

```bash
sudo apt-get install git
git --version
```

## Cloning the repo

```bash
git clone https://github.com/renatomatos79/bjss-aws-demo.git
cd bjss-aws-demo/src/todo-vue
```

## Installing project dependences

```bash
npm install
```

### Compile and minify for production

```bash
npm run build
```

### Building and running our docker image...

```bash
docker image build -t todo:1.0.1 .
docker run -d --name todoapp -p 80:80 todo:1.0.1
```

### Inspect the Network tab and get the public IP

http://18.215.244.189/

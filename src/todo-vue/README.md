## Getting Started

To get up and running, follow these steps:

```bash
npm install
```

### Compile and hot-reload for development

```bash
npm run serve
```

### Compile and minify for production

```bash
npm run build
```

### Lint and fix files

```bash
npm run lint
```

### Building and running our docker image

```bash
docker image build -t todo:1.0.1 .
docker run -d --name todoapp -p 8081:80 todo:1.0.1
```

### Tagging and publishing to docker hub

```bash
docker login
docker tag todo:1.0.1 renatomatos79/bjss:todo-1.0.1
docker image push renatomatos79/bjss:todo-1.0.1
```

### Downloading and running from remote repo

```bash
docker run -d --name todoapp-1.0.1 -p 8081:80 renatomatos79/bjss:todo-1.0.1
```

### Tagging and publishing to aws

```bash
docker image build -t todo:1.0.1 .
docker tag todo:1.0.1 public.ecr.aws/g8g7h5m7/bjss-aws:latest

aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/g8g7h5m7

docker push public.ecr.aws/g8g7h5m7/bjss-aws:latest
```

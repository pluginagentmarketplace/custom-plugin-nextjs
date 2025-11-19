---
name: devops-cloud-skills
description: Master Docker, Kubernetes, Terraform, AWS, Linux, CI/CD, and infrastructure as code. Deploy and manage cloud applications at scale.
---

# DevOps & Cloud Engineering Skills

## Docker Essentials

```dockerfile
FROM python:3.9-slim
WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .
ENV PORT=5000
EXPOSE 5000

CMD ["python", "app.py"]
```

```bash
# Docker commands
docker build -t myapp:1.0 .
docker run -p 5000:5000 myapp:1.0
docker push registry.com/myapp:1.0
```

## Kubernetes Basics

```yaml
# Deployment
apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp
spec:
  replicas: 3
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: myapp
        image: myapp:1.0
        ports:
        - containerPort: 5000
        resources:
          requests:
            memory: "64Mi"
            cpu: "250m"

---
# Service
apiVersion: v1
kind: Service
metadata:
  name: myapp-service
spec:
  type: LoadBalancer
  selector:
    app: myapp
  ports:
  - port: 80
    targetPort: 5000
```

## Terraform Infrastructure

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}

# EC2 Instance
resource "aws_instance" "web" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"

  tags = {
    Name = "Web Server"
  }
}

# S3 Bucket
resource "aws_s3_bucket" "mybucket" {
  bucket = "my-unique-bucket-name"
  acl    = "private"
}

output "instance_ip" {
  value = aws_instance.web.public_ip
}
```

## CI/CD with GitHub Actions

```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-python@v2
        with:
          python-version: 3.9
      - run: pip install -r requirements.txt
      - run: pytest

  build:
    needs: test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: docker build -t myapp:${{ github.sha }} .
      - run: docker push registry/myapp:${{ github.sha }}

  deploy:
    needs: build
    runs-on: ubuntu-latest
    steps:
      - run: kubectl set image deployment/myapp app=registry/myapp:${{ github.sha }}
```

## Linux Command Essentials

```bash
# Navigation
pwd, ls -la, cd /path, mkdir dir, rm file

# Users & Permissions
chmod 755 file.sh
chown user:group file
sudo useradd username

# Process Management
ps aux, kill 1234, top, systemctl start service

# Package Management
apt update && apt install package  # Debian/Ubuntu
yum install package                 # RHEL/CentOS

# Networking
ip addr, netstat -tlnp, ssh user@host
```

## AWS Key Services

```bash
# EC2 - Compute
aws ec2 describe-instances
aws ec2 run-instances --image-id ami-xxx --instance-type t2.micro

# S3 - Storage
aws s3 cp file.txt s3://mybucket/
aws s3 ls s3://mybucket/

# RDS - Database
aws rds describe-db-instances
aws rds create-db-instance --db-instance-identifier mydb

# CloudWatch - Monitoring
aws cloudwatch get-metric-statistics --namespace AWS/EC2
```

## Monitoring & Logging

- **Prometheus**: Metrics collection
- **Grafana**: Visualization dashboards
- **ELK Stack**: Logging (Elasticsearch, Logstash, Kibana)
- **CloudWatch**: AWS native monitoring
- **Datadog**: SaaS monitoring platform

## Infrastructure Scaling

- **Horizontal**: Add more servers (load balancing)
- **Vertical**: Increase server resources
- **Auto-scaling**: Scale based on metrics
- **Caching**: Reduce database load (Redis)
- **CDN**: Distribute content globally

## Key Concepts Checklist

- [ ] Docker images and containers
- [ ] Docker Compose multi-container
- [ ] Kubernetes pods, services, deployments
- [ ] Helm package management
- [ ] Terraform configuration
- [ ] AWS EC2, S3, RDS, VPC
- [ ] CI/CD pipeline setup
- [ ] Monitoring and alerting
- [ ] Log aggregation
- [ ] Infrastructure security
- [ ] Cost optimization
- [ ] Disaster recovery

---

**Source**: https://roadmap.sh

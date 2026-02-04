## Create an ec2 machine
First of all, create a ec2 machine of Ubuntu and t2.large and 30gb storage

## SSH into the machine
run following commands, get ssh of your ec2 machine and install some packages

```
ssh -i "pem-key.pem" ubuntu@ec2-3-88-54-141.compute-1.amazonaws.com

sudo apt update -y

sudo apt install unzip

curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws --version

curl -o kubectl https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin
kubectl version --short --client

curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
sudo mv /tmp/eksctl /usr/local/bin
eksctl version
```


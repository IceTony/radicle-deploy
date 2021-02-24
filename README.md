# radicle-deploy
Deploy Radicle seed node  
More info: https://docs.radicle.xyz/docs/using-radicle/running-a-seed-node
## Create VM
### AWS EC2
1. Install aws cli
```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
rm awscliv2.zip
```
2. Configure aws cli
```
aws configure
...
```
3. Install terraform
```
curl "https://releases.hashicorp.com/terraform/0.14.7/terraform_0.14.7_linux_amd64.zip" -o "terraform.zip"
unzip terraform.zip
sudo mv terraform /usr/local/bin/
rm terraform.zip
```
4. Create EC2 instance
```
cd terraform/aws_ec2
terraform init
terraform apply
```
5. Log-in to instance
```
# get instance ip address
terraform show | grep public_ip

# ssh to instance
ssh ubuntu@1.2.3.4
```
## Deploy Radicle seed node
1. Download and run install script
```
sudo su
cd ~
curl https://raw.githubusercontent.com/IceTony/radicle-deploy/main/radicle.sh | bash -s
```
2. Open in browser: http://1.2.3.4:80
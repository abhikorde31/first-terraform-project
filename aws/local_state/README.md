How to create EC2 Instance(AWS) using terraform on local-state

first install the terraform in your linux terminal using following command
1. Update system packages:
sudo apt update && sudo apt install -y gnupg software-properties-common
2. Add HashiCorp’s official GPG key and repository:
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list

3.Install Terraform:
sudo apt update && sudo apt install -y terraform

after installing verify terraform is installed or not in your system use following command:
terraform -version
if it show version it means terraform is sucessfully.
there is three step in terraform are as follows:

terraform init This command initializes a working directory containing Terraform configuration files. This is the first command you should run after writing a new Terraform configuration or cloning an existing configuration from version control. It is safe to run this command multiple times.
terraform plan This command creates an execution plan, which lets you preview the changes that Terraform plans to make to your infrastructure.
terraform apply This command executes the actions proposed in a Terraform plan.
now we can see practically one by one command:
first write main.tf file using following command:

Image description
This file contains all information about our EC2 instance example region,service provider, instance name, etc
-- vi main.tf

then run first command as we discuss in above section:
ie Terraform Init

if you got above responce then go for the Terraform Plan
It's basically dry run things it's show process will be after apply.
--Terraform plan
--Terraform apply
after using Terraform Apply command, It ask for Enter the value:

type "yes" for creating EC2 instance.
Now we sucessfully created EC2 instance in our aws cloud server
Now open dash board--->EC2 instance---->select region="us-west-2"
you can seen your EC2 Instance:
I use https://developer.hashicorp.com documentation for references

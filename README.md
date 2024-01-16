AWS VPC Infrastructure
This repository contains Terraform code to create an Amazon Web Services (AWS) Virtual Private Cloud (VPC) along with associated resources. The infrastructure includes the following components:

VPC (aws_vpc):

The main VPC with a specified CIDR block (10.0.0.0/16).
Internet Gateway (aws_internet_gateway):

An internet gateway associated with the created VPC to enable communication between instances in the VPC and the internet.
Route (aws_route):

A default route in the main route table of the VPC, directing traffic with the destination CIDR block 0.0.0.0/0 to the internet gateway.
Availability Zones (data.aws_availability_zones):

Data source to dynamically retrieve information about the availability zones in the AWS region.
Subnet (aws_subnet):

Subnets created in each availability zone within the VPC.
Each subnet has a CIDR block of the form 10.0.<availability_zone_index>.0/24.
The map_public_ip_on_launch attribute is set to true, allowing instances launched in these subnets to receive public IP addresses.
Prerequisites
Before using this Terraform code, make sure you have the following prerequisites:

Terraform installed on your local machine.
AWS credentials configured on your machine with the necessary permissions.
Usage
Clone this repository to your local machine:

git clone https://github.com/hmuse05/Two-tier-vpc-terraform.git
cd Two-tier-vpc-terraform

Initialize the Terraform configuration:

terraform init
Review and customize the main.tf file if needed.

Before applying the changes to your AWS infrastructure, you can use the following command to generate and review a Terraform plan:

terraform plan

This command will analyze your Terraform configuration and display the changes that will be made to your infrastructure. It provides a summary of additions, modifications, and deletions.
![image](https://github.com/hmuse05/Two-tier-vpc-terraform/assets/114592592/c7ceb1d3-8499-46e6-8ed3-7df84caa9823)

![image](https://github.com/hmuse05/Two-tier-vpc-terraform/assets/114592592/024c1a2d-c187-42d3-ac17-24845407c15f)

![image](https://github.com/hmuse05/Two-tier-vpc-terraform/assets/114592592/010f454b-d5f0-4bb8-9f2c-714884639a02)

![image](https://github.com/hmuse05/Two-tier-vpc-terraform/assets/114592592/0875dd08-8fcd-4d33-a859-659cb8456aa4)

![image](https://github.com/hmuse05/Two-tier-vpc-terraform/assets/114592592/9f61563d-3032-4fc3-bdcf-e60c45883072)











Apply the Terraform configuration to create the AWS infrastructure:

terraform apply

![image](https://github.com/hmuse05/Two-tier-vpc-terraform/assets/114592592/03f8a721-f372-4724-86aa-6c1e277d9957)

![image](https://github.com/hmuse05/Two-tier-vpc-terraform/assets/114592592/96cc82ad-2b8d-4d85-bc03-303445b9bd41)

![image](https://github.com/hmuse05/Two-tier-vpc-terraform/assets/114592592/ff724ea7-cc62-46e6-86b3-2fb620cc2c15)

![image](https://github.com/hmuse05/Two-tier-vpc-terraform/assets/114592592/f23a6058-b183-4b0d-8c76-28d5ded19694)

![image](https://github.com/hmuse05/Two-tier-vpc-terraform/assets/114592592/0206809e-e3aa-44e3-ad50-79a67fddbde9)






Cleanup
To destroy the created AWS infrastructure, run:

terraform destroy

![image](https://github.com/hmuse05/Two-tier-vpc-terraform/assets/114592592/04655373-a98e-41c7-b066-d44d13907e78)


You will be prompted to confirm the destruction of resources.


# Terraform-3-tier-application

Terraform Achitecture 
Terraform init 
Terraform plan 
Terraform apply
Terraform destroy
Terrform write

resources "aws_instance" "new_instance" {
ami = "ami-2862890e8732897345"
instance_type = "t2.micro"
security_group = "default"
key_name = "mumbai_key"
tags = {
    "Name" = "instance1"
  }
}

provider "aws" {
  region = var.region
  }

 provider "aws" {
   region = "us-east-1"
   } 





resource "aws_vpc" "example" {
  cidr_block = "172.16.0.0/16"

  tags = {
    Name = "tf-example"
  }
}

resource "aws_subnet" "example" {
  vpc_id            = aws_vpc.example.id
  cidr_block        = "172.16.10.0/24"
  availability_zone = "us-east-2a"

  tags = {
    Name = "tf-example"
  }
}

data "aws_ami" "amzn-linux-2023-ami" {
  most_recent = true
  owners      = ["amazon"]

  filter {
    name   = "name"
  
}

resource "aws_instance" "example" {
  ami           = data.aws_ami.amzn-linux-2023-ami.id
  instance_type = "c6a.2xlarge"
  subnet_id     = aws_subnet.example.id

  cpu_options {
    core_count       = 2
    threads_per_core = 2
  }

  tags = {
    Name = "tf-example"
  }
}   

===================================THREE-TIER-PROJECTS======================================

1. 

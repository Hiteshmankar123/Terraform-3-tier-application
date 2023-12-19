# Terraform-3-tier-application

Terraform Achitecture 
Terraform init 
Terraform plan 
Terraform apply
Terraform destroy
Terrform write

resources "aws_instance" "new_instance"
ami = "ami-2862890e8732897345"
instance_type = "t2.micro"
security_group = "default"
key_name = "mumbai_key"


provider
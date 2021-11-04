Terraform module to provision an EC2 instance.

```hcl
terraform {

}

provider "aws" {
  region = "eu-west-1"
}

locals {
  vpc_id     = "A"
  my_ip      = "B"
  public_key = "C"
}

module "apache" {
  source = "./terraform-aws-apache-example"

  server_name = "Phil"
  vpc_id      = local.vpc_id
  my_ip       = local.my_ip
  public_key  = local.public_key
}

output "public_ip" {
  value = module.apache.public_ip
}
```

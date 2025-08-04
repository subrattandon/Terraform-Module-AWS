# This is complete config to use this module



# Usage

provider "aws" {
  region = "eu-north-1"
}
module "vpn" {
    source = "./modules/vpc"
    vpc_config = {
      cidr_block = "10.0.0.0/16"
      Name = "my_vpc"
    }

subnet_config = {
  subnet1 = {
    cidr_block = "10.0.0.0/24"
    az         = "eu-north-1a"
    public     = true
  },
  subnet2 = {
    cidr_block = "10.0.2.0/24"
    az         = "eu-north-1a"
    public     = true
  },
  subnet3 = {
    cidr_block = "10.0.1.0/24"
    az         = "eu-north-1b"
    public     = false
  }
}

}
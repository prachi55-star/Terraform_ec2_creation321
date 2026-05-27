🚀 Terraform AWS EC2 Instance Creation

## Overview

This Terraform project creates an AWS VPC with public and private subnets. It also creates an Internet Gateway (IGW), route tables, route table associations, security groups, and an EC2 instance using Terraform.

## Features

- Creates a VPC with a specified CIDR block
- Creates public and private subnets
- Creates an Internet Gateway (IGW)
- Creates route tables and associations
- Creates Security Group
- Launches EC2 instance in public subnet
- Uses Terraform validations

## Usage

```hcl
vpc_config = {
  cidr_block = "10.0.0.0/16"
  name       = "my-vpc"
}

subnet_config = {
  public_subnet_1 = {
    cidr_block = "10.0.1.0/24"
    az         = "ap-south-1a"
    public     = true
  }

  public_subnet_2 = {
    cidr_block = "10.0.2.0/24"
    az         = "ap-south-1b"
    public     = true
  }

  private_subnet = {
    cidr_block = "10.0.3.0/24"
    az         = "ap-south-1a"
  }
}

ec2_config = {
  instance_type = "t3.micro"
  subnet_name   = "public_subnet_1"
  instance_name = "my-ec2"
}
```
💡
Terraform → AWS Provider → AWS EC2 Instance → VPC → Subnet → Security Group


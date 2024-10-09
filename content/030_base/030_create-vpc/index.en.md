---
title: 'Amazon VPC Architecture'
weight: 30
---

In this chapter, you will create a Terraform stack to provision an Amazon Virtual Private Cloud (VPC) with public and private subnets spanning multiple Availability Zones. The use of multiple Availability Zones ensures high availability and fault tolerance for your resources, as they are distributed across physically separate data centers within the same AWS Region. Public subnets are used for resources that need to be accessible from the internet, such as load balancers or bastion hosts, while private subnets are used for resources that should not be directly accessible from the internet, such as application servers or databases, for enhanced security.

The VPC will include an Internet Gateway for external access and a Network Address Translation (NAT) Gateway to enable outbound internet access for resources in the private subnets. For this workshop, a single NAT Gateway will be used, but in production environments, it is recommended to have a NAT Gateway in each Availability Zone for high availability and fault tolerance.

All the Elastic Kubernetes Service (EKS) clusters created throughout this workshop will be deployed within this VPC.

![Environment architecture diagram](/static/images/environment.jpg)

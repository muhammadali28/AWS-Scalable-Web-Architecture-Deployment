# Scalable-and-Secure-Web-Application-Deployment-on-AWS-Cloud-Infrastructure
![My Image](diagram.png)

## Objective:-
The objective of this project is to deploy a highly available, secure, and scalable web application using Amazon Web Services (AWS).
Deployment Structure:
The deployment is configured in the North Virginia Region, utilizing two Availability Zones (AZs). The architecture components are deployed across the following subnets within a Virtual Private Cloud (VPC):
### VPC and Subnets: 
The VPC consists of two public subnets and three private subnets. The private subnets provide a secure environment for the web servers and databases. The private subnets have internet access through a NAT gateway deployed in the public subnet.
### Amazon Machine Image (AMI) and Launch Template: 
An EC2 instance with IIS and MySQL Workbench/Client installed is deployed in a public subnet. This instance is used to create an AMI and launch template for the Auto Scaling Group (ASG).
### Auto Scaling Group: 
The private web servers are provisioned using an ASG in the private subnet. The ASG ensures the desired number of instances are always available for high availability and scalability. 
Minimum, maximum, and desired instances: 2 VMs

### Elastic Load Balancer (ELB): 
An internet-facing ELB is created, which includes EC2 instances in the target group. The ELB distributes traffic and enables internet users to access the web server page on port 80.
### Bastion Server: 
Enhanced security is implemented by allowing access to the web servers only via a bastion host.
### MySQL RDS: 
A private RDS instance based on MySQL is created. It can only be accessed from the web servers using the MySQL Workbench client.
###  Simple Notification Service (SNS) Notifications: 
Email alerts are configured to receive updates when the ASG launches new instances.

## Key Achievements:
Successful deployment of a web application on Amazon EC2 Windows instances.
Implementation of high availability configuration using separate subnets, Auto Scaling Group, and multiple Availability Zones.
Integration of an ELB for traffic distribution.
Enhanced security by accessing web servers via a bastion host.
Secure integration of MySQL RDS with web servers.
Configuration of SNS notifications for monitoring and updates.

## Challenges:
Ensuring proper security measures and access controls across the various components.
Configuration and management of the network infrastructure, including VPC and subnets.
Setting up and maintaining the Auto Scaling Group for private web servers.
Establishing connectivity and integration between the web servers and RDS instance.

## Service Usage:
The project utilizes various Amazon Web Services (AWS) components, including:
EC2 instances for hosting web servers
Auto Scaling Groups for high availability and scalability
Elastic Load Balancer for distributing traffic
VPC and subnets for network isolation and security
NAT Gateway for internet access from private subnets
Internet Gateway for connecting the VPC to the internet
RDS (MySQL) for hosting the database
SNS for notifications and alerts

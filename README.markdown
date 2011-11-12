# EC2 Easy Proxy
## Introduction
This template allows AWS customers to launch a Squid server in arbitrary region without loggin in to EC2 servers nor executing any command, but putting the template to [AWS CloudFormation](http://aws.amazon.com/cloudformation/).

This project is rather a proof of concept, but I think some people find this template useful in some use cases. Some online services restrict the range of source IPs, but people can quickly launch a web proxy in the US, Ireland, Singapore and Japan with this template. People with such demand may not have good technical skill to log in to Linux instances and then install and configure Squid to achieve their goal.


## How to Deploy
(Hopefully) To be updated.


## Discussions
## EBS-backed vs. Insntance-store?
The template uses EBS-backed AMIs, even though EBS-backed insntances cost a bit more 
than Instance-store type instances. This is intentional, because you cannot run Instance-store 
type instnace on t1.micro, which is the smallest (thus cheapest) type. If you want to run larger types of insntance to proxy more than one client PCs, please consider using Instance-store types instead of EBS-backed ones to reduce the cost of an EBS volume.

For newer users, please note that AWS free tier allows users to launch a t1.micro instance with an EBS volume as its root device for free for the first 12 months after the account creation.


## Interested in CloudFormation?
For those who are interested in AWS CloudFormation, please visit the following sites for more information:
* [AWS CloudFormation - product site](http://aws.amazon.com/cloudformation/)
* [Sample Templates - US East (Virginia) region](http://aws.amazon.com/jp/cloudformation/aws-cloudformation-templates//187-1396276-6211708)
* [AWS CloudFormation Documentation](http://aws.amazon.com/documentation/cloudformation/)


## Update History
2011-11-12: First commit.
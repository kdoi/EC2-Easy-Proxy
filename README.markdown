# EC2 Easy Proxy
## Introduction
This template allows AWS customers to launch a Squid server in arbitrary region without loggin in to EC2 servers nor e\
xecuting any command, but putting the template to [AWS CloudFormation](http://aws.amazon.com/cloudformation/).

This project is rather a proof of concept, but I think some people find this template useful in some use cases. Some o\
nline services restrict the range of source IPs, but people can quickly launch a web proxy in the US, Ireland, Singapo\
re and Japan with this template. People with such demand may not have good technical skill to log in to Linux instance\
s and then install and configure Squid to achieve their goal.

## How to Deploy
0. Create an AWS account, if you don't have one.
1. Save the template to your PC/Mac.
2. Login to the AWS Management Console and open the CloudFormation tab.
3. Choose one of the AWS regions where you want to launch a proxy server and then hit "Create New Stack" button.
4. In "SELECT TEMPLATE": Select "*Upload a Template File*" and point to the template file that you save in step 1. You can leave the other fields as they are, but make sure to type in the Stack Name field with any name you feel comfortable.
5. The next page, "SPECIFY PARAMETERS" asks for template-specific information. With EC2 Easy Proxy, you need to specify the port number you would like to use and your IP address. This template create a firewall called Security Group to restrict other users from using your proxy server.
   Note that IP address needs to be specified with subnet mask. In other words, if you want to specify only one IP address ("1.2.3.4"), then the field should be "1.2.3.4/32"
6. Click Continue twice and finish the wizard.
7. When the status of your stack turns green (CREATE_COMPLETE), then click the outputs tab of the bottom pane of the Management Console to find the IP address of the proxy server.
8. Configure your web browser to use the proxy. Enjoy!

## Discussions
### EBS-backed vs. Insntance-store?
The template uses EBS-backed AMIs, even though EBS-backed insntances cost a bit more
than Instance-store type instances. This is intentional, because you cannot run Instance-store
type instnace on t1.micro, which is the smallest (thus cheapest) type. If you want to run larger types of insntance to\
 proxy more than one client PCs, please consider using Instance-store types instead of EBS-backed ones to reduce the c\
ost of an EBS volume.

For newer users, please note that AWS free tier allows users to launch a t1.micro instance with an EBS volume as its r\
oot device for free for the first 12 months after the account creation.

## Interested in CloudFormation?
For those who are interested in AWS CloudFormation, please visit the following sites for more information:

*   [AWS CloudFormation - product site](http://aws.amazon.com/cloudformation/)
*   [Sample Templates - US East (Virginia) region](http://aws.amazon.com/jp/cloudformation/aws-cloudformation-templates/\
/187-1396276-6211708)
*   [AWS CloudFormation Documentation](http://aws.amazon.com/documentation/cloudformation/)


## Update History
2011-11-12: First commit.

# Wordpress cloudformation
AWS CloudFormation template used by Launch Learning Website

## AMI
The cloudformation uses the Linux 2 AMI

## Regions
The template is configured to work in regions eu-west-1 and eu-west-2
Additional regions may be used by first adding the appropriate Linux 2 AMI ID in the Mappings section of the template.
The template relies on selecting 3 subnets as 3 Elastic File System mount targets are configured.

## Packages
Installs the latest version of wordpress and php version 7.3.

## Security
The template relies on having a SSL certificate within AWS Certification Manager. The certificate should be created in the region you wish to run the load balancer and must reference the WordPress domain name.
The certificate ARN is entered as a parameter during stack launch.

## Auto Scaling
The Web Server Group is configured to use a minimum of 1 instance and a maximum of 3. These can be adjusted in the template or by adding them as a template parameter to select during stack launch.

## Elastic File System
EFS stores any modifications and plugins added to the wordpress installation, therefore any new instances will be launched with the latest version of the website.

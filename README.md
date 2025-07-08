# AWSCloudProject1
Step1 - AWS Console login
Step2 - Create Inbound Rule (HTTP) in Security Group
Step3 - Create Target Groups with empty targets (ie:EC2)
Step4 - Cteare ALB (Application Load Banlancer) -> Select created Target Group
Step5 - Create launch template with user-data

user-data
#!/bin/bash
yum install httpd -y
systemctl start httpd
systemctl enable httpd
chkconfig httpd on
mkdir /var/www/html
echo 'Hey! This is my First ASG' > /var/www/html/index.html

Step6 - Create ASG (Auto Scaling Group) -> Select Launch Template -> Create SNS for Notification 
Step7 - Access DNS Name -> ALB -> Hit it on browser

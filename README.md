# AWSCloudProject1 ⛳
Step1 - AWS Console login  

Step2 - Create Inbound Rule (HTTP) in Security Group  

Step3 - Create Target Groups with empty targets (ie:EC2)  

Step4 - Cteare ALB (Application Load Banlancer) -> Select created Target Group  

Step5 - Create launch template with user-data

-------------------------
user-data  
-------------------------
#!/bin/bash  

yum install httpd -y  

systemctl start httpd  

systemctl enable httpd  

chkconfig httpd on  

mkdir /var/www/html  

echo 'Hey! This is my First ASG' > /var/www/html/index.html

-------------------------

Step6 - Create ASG (Auto Scaling Group) -> Select Launch Template -> Create SNS for Notification   

Step7 - Access DNS Name -> ALB   

Step8 - Hit it on browser Now you access static web page  

Step9 - You have to change data in user-data
        Nevigate to -> launch template -> update user-data -> create launch template with version 2 -> 
        go to ASG -> edit it with version 2 -> and select instant refresh -> Note: while creating ASG slect instance maintainence ploicy as launch before termination
	
Step10 - now access DNS Name in ALB hit on browser you will get updated web page




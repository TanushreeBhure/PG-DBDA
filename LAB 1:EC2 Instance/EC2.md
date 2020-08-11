# LAB 1:EC2 INSTANCE
## About this Lab   
***Objective**: To create a EC2 resources and launch EC2 Instance*  
***File locations**:*  
***Successful outcome**: You will be able to create and launch EC2 Instance.*  
***Before you begin**:  Login to AWS Console.*  
***Related lesson**: Amazon EC2- Amazon Web Services*    

**LAB STEPS:**  
1.Open the Amazon EC2 console at AWS.    
2.Choose launch instances.    
3.In Step 1: Choose an Amazon Machine Image (AMI), find an Amazon Linux AMI at the top of the list and choose Select.
In Step 2: Choose an Instance Type t2.micro 1GB 1CPU, choose Next: Configure Instance Details.  
In Step 3: Configure Instance Details,No of instances as 1, choose Next:Add Storage.  
In step 4: Add Storage, configure size as 30GB, Choose Next:Add Tags.  
In step 5: Add Tags, Give key and value, Choose Next:Configure Security Groups.  
In step 6: Configure security groups, Select exisiting security group or provide following information if you want to create new security group-  
Type: SSH   
Protocol: TCP  
Port Range: 22  
Source: Anywhere 0.0.0.0/0  
In step 7: Choose Review and Launch.  
4.Choose Launch.  
5.Select the check box for the key pair that you created or create a new key. Give key pair name and Download the key pair,and then choose Launch Instances.  
6.Wait for instance to show running state.   

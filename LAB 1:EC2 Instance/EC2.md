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
![1](https://user-images.githubusercontent.com/63635084/89877148-4d56a200-dbdd-11ea-8d3a-43a35f5549e2.png)  


In Step 2: Choose an Instance Type t2.micro 1GB 1CPU, choose Next: Configure Instance Details.
![2](https://user-images.githubusercontent.com/63635084/89877865-572cd500-dbde-11ea-9b6f-af719256fb14.png)  


In Step 3: Configure Instance Details,No of instances as 1, choose Next:Add Storage.  
![3](https://user-images.githubusercontent.com/63635084/89877925-74fa3a00-dbde-11ea-80b8-1103370098f3.png)  


In step 4: Add Storage, configure size as 30GB, Choose Next:Add Tags.  
![4](https://user-images.githubusercontent.com/63635084/89877936-77f52a80-dbde-11ea-9919-7d687383ab5a.png)  


In step 5: Add Tags, Give key and value, Choose Next:Configure Security Groups.  
![5](https://user-images.githubusercontent.com/63635084/89877948-7c214800-dbde-11ea-945b-f109e697ed8c.png)  


In step 6: Configure security groups, Select exisiting security group or provide following information if you want to create new security group-  
Type: SSH   
Protocol: TCP  
Port Range: 22  
Source: Anywhere 0.0.0.0/0  
![6](https://user-images.githubusercontent.com/63635084/89877954-7f1c3880-dbde-11ea-918f-4271ca693a28.png)  


In step 7: Choose Review and Launch.  
![7](https://user-images.githubusercontent.com/63635084/89877967-82172900-dbde-11ea-8ff4-453a06c1c190.png)  


4.Choose Launch.  
5.Select the check box for the key pair that you created or create a new key. Give key pair name and Download the key pair,and then choose Launch Instances. 
![8](https://user-images.githubusercontent.com/63635084/89877985-88a5a080-dbde-11ea-9435-303c3b1632e0.png)  


6.Wait for instance to show running state.  
![Screenshot (38)](https://user-images.githubusercontent.com/63635084/89878853-bdfebe00-dbdf-11ea-81c3-838ec9131eaa.png)  



# LAB 2: EMR CLUSTER  
## About this Lab   
***Objective**: To create a new hadoop cluster on Amazon EMR*  
***File locations**:*  
***Successful outcome**: You will be able to create cluster on Amazon EMR.*  
***Before you begin**:  Login to AWS Console.*  
***Related lesson**: Amazon EMR- Amazon Web Services*    

**LAB STEPS:**

1.Go to AWS services. Search for EMR and Click on EMR.  
2.Click on "CREATE CLUSTER".  
3.In cluster configuration we need to give cluster name, uncheck logging, select software configuration i.e core you will be using. Here, we have used m4.large in Hardware Configuration, number of instances as 1.  
![11](https://user-images.githubusercontent.com/63635084/89880190-9872b400-dbe1-11ea-803d-bb5bcb15619c.png)  

4.Now, In security and access use your ec2 key pair for ssh to the instance and click on create cluster. 
![22](https://user-images.githubusercontent.com/63635084/89880184-96a8f080-dbe1-11ea-8c4b-6b5a75502734.png)  

5.Instance will require approx 10 minutes to get into running state.  
![33](https://user-images.githubusercontent.com/63635084/89880188-9872b400-dbe1-11ea-83b1-761a7c62cd32.png)  

6.When cluster shows "waiting state" it means cluster is ready to use.
![1](https://user-images.githubusercontent.com/63635084/89882722-d6250c00-dbe4-11ea-9f00-c3d8365a63a3.png)  

7.Go to Hardware Configuration and copy the public ip address to access master node. 
![2](https://user-images.githubusercontent.com/63635084/89882731-d91ffc80-dbe4-11ea-81eb-272841dc2949.png)  
8.Use any tool for remote computing. Create and connect to new SSH using this public ip address.  
9.This completes the process of EMR Cluster.

***Conclusion**: We have learnt to create EMR cluster on Amazon Web Services.*







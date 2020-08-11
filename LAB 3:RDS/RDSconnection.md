# RDS Database Connection  
***Objective**:How to connect a RDS database to local database system  
**Steps-**A database created on RDS*  
Note: To learn how to create a new database, [click](https://github.com/TanushreeBhure/PG-DBDA/blob/Cloud-Computing/LAB%203:RDS/RDS.md) on the link.  
1. The data base you want to connect should be up and running.  
2.To connect RDS database instance to MySQL Workbench which is already installed on local system.Steps are as follows:  
In the MySQL Workbench Click on Setup new Connection,  
Give the Connection name and Select the Connection method as Standard TCP/IP,  
Enter the host name from RDS end point and port as 3306,  
Enter Mysql user name.  
3.Click on "Store in vault" to add password.  
4.Enter the password as given in RDS instance creation, and click "OK".  
5.Then test the connection and click ok.  
6.If you get a Success message, it means that your connection was successfully established. And click on "Ok".  
7.Click "Ok" and start working with your RDS Database.  

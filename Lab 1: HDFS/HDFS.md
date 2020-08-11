# LAB 1: USING HDFS COMMANDS   
## About this Lab   
***Objective**:  To become familiar with how files are added to and removed from HDFS and how to view files in HDFS.  
**File locations**:    
**Successful outcome**:  You have added and deleted several files and folders in HDFS.  
**Before you begin**:  Your HDP 2.3 cluster should be up and running within your VM.  
**Related lesson**: The Hadoop Distributed File System (HDFS)    
**Prerequisites**: EMR Cluster    
To create a new hadoop cluster on Amazon EMR [click](https://github.com/TanushreeBhure/PG-DBDA/blob/Cloud-Computing/LAB%202:%20EMR%20Cluster/EMR.md) here.*  

## LAB STEPS  

1. Download the labs file into emr and unzip it  
wget https://dbda-labs.s3.amazonaws.com/labs.zip
unzip labs.zip  

2.**View the hdfs dfs Command**      
a.Open session in MobaXtreme and connect through ssh.  
b.Enter the following command to view the usage of hdfs dfs:   
```hdfs dfs```  
![1](https://user-images.githubusercontent.com/63635084/89894986-ac75e000-dbf8-11ea-8699-1de427a972a6.png)  

*Notice that the usage contains options for performing filesystem tasks in HDFS,like copying files from a local folder into HDFS, retrieving a file from HDFS, copying and    
files around, and making and removing directories. In this lab, you will perform these commands, and many others, to help you become comfortable with working with HDFS.*    

3.**Create a Directory in HDFS**   
a.Enter the following -ls command to view the contents of the user’s root directory in HDFS, which is /user/root  
```hdfs dfs -ls```  
You do not have any files in /user/root yet, so no output is displayed.   
Run the -ls command again, but this time specify the root HDFS folder:     
```hdfs dfs -ls /```  
The output should look similar to:  
![2](https://user-images.githubusercontent.com/63635084/89895494-8ac92880-dbf9-11ea-82ec-6dd9ed8ca896.png)  
*Important:Notice how adding the / in the -ls command caused the contents of the root folder to display, but leaving off the / showed the contents of /user/root, which is the default prefix if you leave off the leading / on any of the hadoop commands (assuming the command is run by the “root” user).*   
b. Enter the following command to create a directory named test in HDFS:   
```hdfs dfs -mkdir test```  
c. Verify that the folder was created successfully:   
```hdfs dfs -ls```  
![3](https://user-images.githubusercontent.com/63635084/89895746-f57a6400-dbf9-11ea-8f79-388666a89bb6.png)  
d. Create a couple of subdirectories for test:   
```hdfs dfs -mkdir test/test1```  
```hdfs dfs -mkdir -p test/test2/test3```  
*Notice how the -p command can be used to create multiple directories. The second command above will fail if you omit the -p.*    
e. Use the -ls command to view the contents of /user/root:   
```hdfs dfs -ls```  
Notice you only see the test directory. To recursively view the contents of a folder,   
```use -ls -R:```   
```hdfs dfs -ls -R```    
The output should look like:  
![4](https://user-images.githubusercontent.com/63635084/89896141-91a46b00-dbfa-11ea-92ea-3159f7f33f2d.png)

3.**Delete a Directory**   
a. Delete the test2 folder (and recursively, its subcontents) using the -rm -R command:   
```hdfs dfs -rm -R test/test2```  
b. Now run the -ls -R command:   
```hdfs dfs -ls -R```  
The directory structure of the output should look like:  
![5](https://user-images.githubusercontent.com/63635084/89896400-037cb480-dbfb-11ea-9207-7b78bf19cefc.png)  
*Note:Notice Hadoop created a .Trash folder for the root user and moved the deleted content there. The .Trash folder empties automatically after a configured amount of time.*    

4.**Upload a File to HDFS**  
a. Now let’s put a file into the test folder. Change directories to /root/devph/labs/Lab2.1:   
```cd /root/devph/labs/Lab2.1/```
b. Notice this folder contains a file named data.txt: 
```tail data.txt```
c. Run the following -put command to copy data.txt into the test folder in HDFS: 
```hdfs dfs -put data.txt test/```  
![6](https://user-images.githubusercontent.com/63635084/89897406-9833e200-dbfc-11ea-99cf-1ef22c8e358e.png)  

5.**Copy a File in HDFS**     
a. Now copy the data.txt file in test to another folder in HDFS using the -cp command:    
```hdfs dfs -cp test/data.txt test/test1/data2.txt```  
b. Verify that the file is in both places by using the -ls -R command on test. The output should look like the following:   
```hdfs dfs -ls -R test```   
c. Now delete the data2.txt file using the -rm command:   
```hdfs dfs -rm test/test1/data2.txt```  
d. Verify that the data2.txt file is in the .Trash folder.  
![7](https://user-images.githubusercontent.com/63635084/89897637-f3fe6b00-dbfc-11ea-92a7-3b95dab87c9a.png)  

6.**View the Contents of a File in HDFS**   
a. You can use the -cat command to view text files in HDFS. Enter the following command to view the contents of data.txt:   
```hdfs dfs -cat test/data.txt```  
![8](https://user-images.githubusercontent.com/63635084/89897982-8b63be00-dbfd-11ea-87db-8a0a19e90fb6.png)  
b. You can also use the ‐tail command to view the end of a file:  
```hdfs dfs -tail test/data.txt```  
![9](https://user-images.githubusercontent.com/63635084/89897988-8d2d8180-dbfd-11ea-9568-a7e6790ceb30.png)  
Notice the output this time is only the last 20 rows of data.txt     

7.**Getting a File from HDFS**   
a. See if you can figure out how to use the get command to copy test/data.txt from HDFS into your local /tmp folder.   
Answer:  
```hdfs dfs -get test/data.txt /tmp/```  
```cd /tmp``` 
```ls data*```  
![10](https://user-images.githubusercontent.com/63635084/89898443-5f950800-dbfe-11ea-87cf-9a1970d33c63.png)  

8. **The getmerge Command**  
a.Put the file /root/devph/labs/demos/small_blocks.txt into the test folder in HDFS. You should now have two files in test: data.txt and small_blocks.txt.    
Answer:  
```hdfs dfs -put /root/devph/labs/demos/small_blocks.txt test/```  
b. Run the following getmerge command:   
```hdfs dfs -getmerge test /tmp/merged.txt```  
c. What did the previous command do? Did you open the file merged.txt to see what happened?
![11](https://user-images.githubusercontent.com/63635084/89898880-11343900-dbff-11ea-87ca-83cae6b777a4.png)  
Answer: The two files that were in the test folder in HDFS were merged into a single file and stored on the local file system.  

9.**Specify the Block Size and Replication Factor**   
a. Put /root/devph/labs/Lab2.1/data.txt into /user/root in HDFS, giving it a blocksize of 1,048,576 bytes.     
*Hint :The blocksize is defined using the dfs.blocksize property on the command line.*   
Answer:  
```hdfs dfs -D dfs.blocksize=1048576 -put data.txt data.txt```  
b. Run the following fsck command on data.txt:   
```hdfs fsck /user/root/data.txt```  
![12](https://user-images.githubusercontent.com/63635084/89899675-42f9cf80-dc00-11ea-81a5-06df69a043fb.png)  
c. How many blocks are there for this file?   
Answer: The file should be broken down into two blocks.  

***Result**:You have just completed Lab 1 which focused on the basics of the HDFS and how to perform the following basic commands on the platform.  

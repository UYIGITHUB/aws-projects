This project creates a VPC, S3 BUCKET, EC2 INSTANCE , IAM ROLE, internet gateway and using CLI through instance public IP connection to ssh from the instance to the s3 bucket to copy, upload and delete files on both directions. 

![Project architecture](<images/20230724194840.png>)

## Step 1

create a vpc 

Search for VPC then click on VPC as shown below.

![Alter test](<images/>)

![Alter test](<images/20230717190741.png>)

Click on CREATE VPC

![Alter test](<images/20230717185817.png>)

Click VPC only
Enter a name for your VPC
Enter an IPv4 CIDR for the VPC connects
Then everything else should be left as default.


![Alter test](<images/20230717190706.png>)

Click CREATE VPC

![Alter test](<images/20230717190447.png>)


Ensure that the vpc is created successfully.
Click on subnets


![Alter test](<images/20230717190622.png>)

Step 2 
click on CREATE SUBNET

![Alter test](<images/20230717190934.png>)

Select the vpc that was created

![Alter test](<images/20230717191135.png>)


Enter a name for the subnet.

Select the AZ for your subnet.

Enter an IP address for the subnet.

![Alter test](<images/20230717191328.png>)

Click CREATE SUBNET

![Alter test](<images/20230717191525.png>)

Ensure your subnet is created successfully.
Click Internet gateway.

![Alter test](<images/20230717192023.png>)

Step 3

Click on create internet gateway

![Alter test](<images/20230717192214.png>)

Enter a name for the IGW.
Click create IGW

![Alter test](<images/20230717192356.png>)

Click attach to vpc

![Alter test](<images/20230717192513.png>)

Click available VPCs to select the VPC you want to attach the internet gateway to.
Then select attach internet gateway to complete attacheing the IGW.

![Alter test](<images/20230724195310.png>)

Confirm to see that it is displaying attached.

![Alter test](<images/20230724195534.png>)

On the left hand side, select Route table. This is to allow traffic from the subnet to be sent directly to the internet gateway.

![Alter test](<images/20230724195731.png>)


Create a route table.

![Alter test](<images/20230724200014.png>)


Enter a name for the route table.
Select the right VPC that route table should be associated with.
Create the route table. 


![[Pasted image 20230724200241.png]]

Ensure the route table was created successfully.
Select edit routes to connect the rout table to the IGW.

![[Pasted image 20230724200751.png]]

Add a route to the table.

![[Pasted image 20230724200829.png]]

The destination is 0.0.0.0/0 which is the open internet.
The target is the internet gateway IGW.

![[Pasted image 20230724201006.png]]


Select the internet gateway that was created earlier which is associated with right VPC.
Save changes.

![[Pasted image 20230724201216.png]]


Ensure the route table was successfully edited.
Select the Subnet association, to allow traffic to be sent the desired subnet inside the VPC. 
![[Pasted image 20230724201352.png]]

Edit subnet associations.

![[Pasted image 20230724201549.png]]

Tick the box of the required subnet.
Save the association.

![[Pasted image 20230724201727.png]]

Step 4.
 Create an S3 bucket.
 ![[Pasted image 20230724202106.png]]

![[Pasted image 20230724202144.png]]


Choose a bucket name and the region you want the bucket to be hosted. 

![[Pasted image 20230724202305.png]]

All other settings should be left at default.
Create bucket.

![[Pasted image 20230724202459.png]]

Ensure the bucket is successfully created.
Click the bucket that was created to upload files. 

![[Pasted image 20230724202709.png]]

Upload the files in your bucket.
![[Pasted image 20230724202930.png]]

Add files.
![[Pasted image 20230724203042.png]]


Upload files. 
![[Pasted image 20230724203300.png]]

Step 5 

Search and select IAM to allocate permission to the EC2. 

![[Pasted image 20230724203505.png]]



Create Policy.
![[Pasted image 20230724214328.png]]

Create a policy name. 
![[Pasted image 20230724213812.png]]
Select S3
![[Pasted image 20230724211740.png]]

For security reason, only the required permissions needed to complete this project will be assigned to the role to be attached to the EC2 instance. 
Check the boxes in Red.
![[Pasted image 20230724211955.png]]

![[Pasted image 20230724212411.png]]

![[Pasted image 20230724212720.png]]

![[Pasted image 20230724212911.png]]

Enter the following Information.
![[Pasted image 20230724212954.png]]

Go to the S3 bucket to copy these information.

![[Pasted image 20230724213102.png]]

![[Pasted image 20230724213417.png]]

Ensure the bucket is displayed.
Select any for Object
Click next.
![[Pasted image 20230724231307.png]]

Create a policy.
![[Pasted image 20230724213559.png]]

Ensure the policy is created successfully.
![[Pasted image 20230724213925.png]]

Create a Role

![[Pasted image 20230724214452.png]]


Select AWS service.
Select EC2
Click next.
![[Pasted image 20230724214552.png]]

Select the right policy that was created earlier. 

![[Pasted image 20230724214724.png]]

Click next.
![[Pasted image 20230724214826.png]]

Create a role name.
Describe the function of the role.
![[Pasted image 20230724214937.png]]

Create the role
![[Pasted image 20230724215048.png]]

Ensure the role is successfully created.

![[Pasted image 20230724215231.png]]

Step 6

Search and create and EC2 Instance
![[Pasted image 20230724215530.png]]

Select the Lunch EC2
![[Pasted image 20230724215708.png]]

Enter EC2 instance name.
![[Pasted image 20230724215849.png]]

Select proceed without a key pair.
![[Pasted image 20230724220040.png]]

Edit security group.
![[Pasted image 20230724220200.png]]

Select the appropriate VPC.
Select the right subnet to make public.
Enable the auto-assign pubic IP.
Select to create a security group.
Name the security group.
Describe the function of the security group.
![[Pasted image 20230724220357.png]]


Create an SSH from anywhere
![[Pasted image 20230724222058.png]]

Attach the Iam role that was created earlier.

![[Pasted image 20230724221619.png]]

Lunch instance.
![[Pasted image 20230724221740.png]]

Ensure instance is successfully created.
![[Pasted image 20230724222155.png]]

Ensure the instance is in a running state and the status check is passed.
![[Pasted image 20230724222452.png]]

Step 7

Test connection between EC2 and S3
![[Pasted image 20230724222851.png]]

Click connect.
![[Pasted image 20230724223656.png]]

This page shows that a connection as been established with the S3 bucket.

![[Pasted image 20230724223844.png]]

For further testing,
aws s3 ls
This is to list the bucket available in the s3

![[Pasted image 20230724224927.png]]

aws s3 ls s3://mybucket-s3-ec2
This is to list the contents within the s3 bucket.

![[Pasted image 20230724225220.png]]
aws s3 cp s3://mybucket-s3-ec2/EVE.PDF EVE.PDF

![[Pasted image 20230724232812.png]]

aws s3 sync s3://mybucket-s3-ec2 mybucket-s3-ec2

This is to copy all the objects in the bucket into the EC2 at once

![[Pasted image 20230725001204.png]]
```

ls - list                              website  

cp - copy                              mv  - move 

rm - remove objects                    sync- synchronise 

mb - create bucket                     rb  -  delete or remove bucket

```

Deleting objects in the EC2 USING CLI

![[Pasted image 20230725002323.png]]
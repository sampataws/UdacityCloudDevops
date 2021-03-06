##Network and Security
* Subnet groups are needed for deploying in multiple AZs.
* We want to place our RDS in more than one Availability Zone (data center). We can place the RDS in two AZs to eliminate single point of failure and to have high availability.
* We created 4 subnets (2 private and 2 public), so the RDS can potentially be duplicated in all four subnets.
* However, keep in mind that we usually prefer to put databases in a private subnet, for security. There may be use cases where you put a database in a public subnet but generally put it in the private subnets.
##Database Accessibility
Usually, don't make a database public.

    * We'll choose "No" for public accessibility" to keep a database private.
    * We'd normally use a private IP address to access a database.
##Availability Zone (AZ)
Let AWS choose the availability zone. Choose "no preference."

##VPC Security Groups
**Default** means every resource in the VPC can talk to any other resource that is within that same VPC. We'll keep this default, to allow resources in the VPC to reach the database.

##Encryption
We can use encryption for sensitive production workloads. We can disable encryption for our database here.

##RDS Running cost notice
If your AWS account is older than one year, you may be outside of the free tier they provide. If so, be sure to delete any RDS databases that you don’t need once you are done practicing because it can be very expensive if you forget it and leave it running for a while!


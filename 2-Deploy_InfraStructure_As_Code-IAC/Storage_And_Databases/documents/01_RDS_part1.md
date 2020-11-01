##Persisting Data
* Most applications need their data to persist and not be lost, which requires a database.
* We don't want a database to be a single point of failure, so we'll use resources that are designed for reliability. For example, RDS for the database, and S3 for the filestore.
* Relational Database Service (RDS): AWS service for creating databases.
##Choosing a database
* AWS Aurora and MySQL have no additional licensing costs. Microsoft SQL Server will have additional licensing costs.
##Mult-AZ deployment
* If you are using a database in a development environment, you can save money by using a single Availability Zone.
* For production databases, use multiple AZs for reliability. If one AZ fails, the other one will still be available.
##A single RDS Server can host multiple databases
* Note that you can use a single RDS database that hosts multiple applications, each with different logins and users for those applications. In other words, you don’t need to create a separate RDS service for each application.
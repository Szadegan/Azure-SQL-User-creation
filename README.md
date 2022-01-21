# How to add a user to Azure SQL Database
This tutorial explains how to create a user on Azure SQL Database and assign a role to that user.

## First Step
On Azure SQL "Master" database in "System Databases"
```
CREATE LOGIN <username> WITH PASSWORD = '<password>';
CREATE USER <username> FOR LOGIN <username>;
```

## Second step
On Azure SQL specific(e.g staging, production,...) db
```
USE [database-name]
GO
CREATE USER <username> FOR LOGIN <username>;
ALTER ROLE db_owner ADD MEMBER <username>; 
```

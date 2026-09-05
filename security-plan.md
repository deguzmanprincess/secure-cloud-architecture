# Secure Cloud Architecture Plan

## CDN
Base on what i understand about cdn or Content Delivery Network it is use to distribute edge locations, it reduce load on the origin server, and it is in between of user and origin server that makes the cached content is served closer to users.

## Load Balancer
the load balancer its distribute the incoming traffic from the multiple server, it helps to improve the performance especially when the traffic is higher or too many it is more like redundancy because it supports availability when one server fails.
 
## Application Server
the application servers it is a process of requests from the users that where in these servers should be placed in a private subnet.

## Database
database where in all the data will be stored it is like a container but it should be in private and don't make it available through internet because most of the data stored here are personal and confidential.

# Security Controls

## IAM
i guess the authorized user can only access this because it a personal identity that need permission if you want to access someone IAM.

## MFA
it should be required to those important accounts example for administrator accounts and other accounts with important privileges because it adds a additional security to prevent unauthorized access and to have valid authentication that identify that its you

## Firewall / Security Group
it is just like the IAM but the firewall or security group should only allow necessary connections

## Encryption
to protect it from leaking and unauthorized access because the work of encryption is to protect and secure the data both when it stored in data base and also during transmission of the data.

## Logging
The system should always record the important activities such as login attempts, user account changes, permission changes, application access, and database access to trace or track what activity does the user do so that to have this it easily identify the security incidents or if its hacked by someone.

## Monitoring
The system should monitor suspicious activities such as repeated failed login attempts and unauthorized access attempts.

# Principle of Least Privilege

## Administrator
allowed to access full system and cloud management

## Instructor
allowed to View and manage authorized student

## Student
allowed to View their own authorized student information

## Developer
allowed to access the development resources and application code, but not the unnecessary production or database administration privileges

# Shared Responsibility Model

## Physical data center
Cloud Provider

## Physical servers
Cloud Provider

## User accounts
Customer

## Student data
Customer

## IAM permissions
Customer

## Application security
Customer

## Database access rules 
Customer

## Backups
Customer

## 1. What does Security OF the Cloud mean?
this is a security that managed by the cloud provider which is these are the physical data centers, servers, and network infrastructure.

## 2. What does Security IN the Cloud mean?
this is a security that manage by the customer by their user accounts, IAM permissions, application security, database access, and data protection.

## 3. Which resource should be directly accessible from the Internet?
i think the load Balancer is the one should be directly accessible from the Internet.

## 4. Why should the database remain private?
The database should remain private and don't put it to the internet to protect student information from unauthorized access.

## 5. Why should users not connect directly to the database?
Users should not connect directly to the database to prevent unauthorized access and protect the data.

## 6. What is the purpose of a load balancer?
load balancer distributes the incoming traffic across multiple application servers and it improves it by redundancy if the one fails it continue to others and especially when the traffic is getting higher

## 7.What happens if one application server fails?
as i said in the purpose of load balancer if one of the application server fails, the load balancer sends traffic to the other available server.

## 8. What is the purpose of a CDN?
it is in between of the users and origin server that helps to delivers website content faster by using servers closer to users.

## 9. Why should administrator accounts use MFA?
to provide extra protection against unauthorized access.

## 10. Why should administrator access not be given to every employee? 
to prevent increasing risk of unauthorized or accidental changes.

## 11. Why are logging and monitoring important?
to help in detecting and investigating some suspicious activities.

## 12. Why are backups important?
it is important because each users are allow data to be restored after data loss or system failure.








# Secure Cloud Architecture Plan

## Architecture

The proposed architecture follows this flow:

Users  
↓  
CDN  
↓  
Load Balancer  
↓  
Application Servers  
↓  
Private Database

## CDN

The CDN stores cached copies of static content closer to users. This improves website loading speed and can help protect the application from some types of traffic attacks.

## Load Balancer

The load balancer receives incoming requests from users and distributes them across multiple application servers. This improves availability and prevents one server from handling all the traffic.

## Application Servers

Application servers process requests from users and provide the application's functionality. These servers should be placed in a private subnet so they are not directly accessible from the Internet.

## Database

The database stores student records and other application information. The database should remain private and should not be directly accessible from the Internet.

# Public and Private Resources

| Resource | Public or Private? | Explanation |
|---|---|---|
| CDN | Public | Users need access to content delivered through the CDN. |
| Load Balancer | Public | It receives incoming requests from users on the Internet. |
| Application Server | Private | Application servers should not be directly accessible from the Internet. |
| Database | Private | Student information should be protected from direct Internet access. |

# Security Controls

## IAM

Identity and Access Management controls who can access the cloud environment and what actions they can perform. Users should only receive permissions necessary for their job.

## MFA

Multi-Factor Authentication should be enabled for administrator accounts and other accounts with important privileges. MFA provides an additional layer of protection if a password is compromised.

## Firewall / Security Group

The firewall or security groups should only allow required connections.

Example rules:

- Internet → Load Balancer = Allowed
- Load Balancer → Application Server = Allowed
- Application Server → Database = Allowed
- Internet → Database = Blocked

Only required ports and protocols should be allowed.

## Encryption

Student information should be encrypted both while being transmitted and while stored. Encryption helps prevent unauthorized users from reading sensitive information.

## Logging

The system should record important activities such as login attempts, account changes, permission changes, application access, and database access.

## Monitoring

The system should monitor suspicious activities such as repeated failed login attempts, unusual network traffic, unauthorized access attempts, and unexpected changes to resources.

## Backup

The database should have regular backups so student information can be restored if data is accidentally deleted, corrupted, or affected by an incident.

# Principle of Least Privilege

Users should receive only the access required to perform their responsibilities.

| User | Allowed Access |
|---|---|
| Administrator | Full system and cloud management access. |
| Instructor | View and manage authorized student records. |
| Student | View their own authorized student information. |
| Developer | Access development resources and application code, but not unnecessary production or database administration privileges. |

Administrator access should not be given to everyone.

# Shared Responsibility Model

| Responsibility | Cloud Provider or Customer? |
|---|---|
| Physical data center | Cloud Provider |
| Physical servers | Cloud Provider |
| User accounts | Customer |
| Student data | Customer |
| IAM permissions | Customer |
| Application security | Customer |
| Database access rules | Customer |
| Backups | Customer |

## Security OF the Cloud

Security OF the Cloud refers to the security responsibilities handled by the cloud provider. This includes protecting physical data centers, physical servers, networking infrastructure, and other underlying cloud infrastructure.

## Security IN the Cloud

Security IN the Cloud refers to the security responsibilities handled by the customer. This includes protecting user accounts, managing IAM permissions, securing applications, controlling database access, protecting data, and configuring security controls.

# Architecture Questions

## 3. Which resource should be directly accessible from the Internet?

The CDN and public load balancer can be accessible from the Internet. The load balancer acts as the controlled entry point to the application.

## 4. Why should the database remain private?

The database contains student information and should be protected from unauthorized Internet access. Keeping it private reduces the attack surface.

## 5. Why should users not connect directly to the database?

Users should access the application instead of connecting directly to the database. The application servers can authenticate users and control which data they are allowed to access.

## 6. What is the purpose of a load balancer?

A load balancer distributes incoming traffic across multiple application servers. It improves performance, availability, and reliability.

## 7. What happens if one application server fails?

If one application server fails, the load balancer can send requests to the other available application server. This allows the application to continue operating.

## 8. What is the purpose of a CDN?

A CDN delivers cached content from locations closer to users. This improves loading speed and can reduce the amount of traffic sent to the application servers.

## 9. Why should administrator accounts use MFA?

Administrator accounts have powerful permissions. MFA provides an additional security layer and makes unauthorized access more difficult if an administrator's password is stolen.

## 10. Why should administrator access not be given to every employee?

Giving administrator access to everyone violates the principle of least privilege. Excessive permissions increase the risk of accidental or malicious changes.

## 11. Why are logging and monitoring important?

Logging records important activities while monitoring helps identify suspicious behavior. Together, they help detect security incidents and support investigation.

## 12. Why are backups important?

Backups allow the organization to restore important student information after accidental deletion, corruption, system failure, or a security incident.

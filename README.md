# Secure Cloud Architecture

## Student Information

Name: De Guzman, Princess Ann S.  
Section: CCIS7E  
Course: BSIT-NETAD  
Date: September 5, 2026

## Project Description

This activity demonstrates a proposed secure cloud architecture for a Student Management Application.

The application allows users to view student information while applying basic cloud networking and security concepts.

## Architecture

Users → CDN → Load Balancer → Application Servers → Private Database

## Security Controls

- IAM
- MFA
- Firewall / Security Groups
- Private Subnets
- Encryption
- Logging
- Monitoring
- Backups

## Public and Private Resources

- CDN – Public
- Load Balancer – Public
- Application Servers – Private
- Database – Private

## Shared Responsibility Model

The cloud provider is responsible for security OF the cloud, such as physical data centers and physical servers.

The customer is responsible for security IN the cloud, such as user accounts, IAM permissions, application security, database access rules, and student data.

# Saudi Social Development Bank

A backend solution developed for the Saudi Social Development Bank to support banking data integration, transaction processing, spending analysis, and personal financial management through reliable and scalable APIs.

## Overview

The project provides backend services that connect the application with external banking data through **Len APIs**, allowing customers to link accounts from multiple banks and retrieve their banking transactions in one place.

The system processes and analyzes the collected transaction data to provide customers with spending insights, transaction categorization, and financial goal tracking.

The project was designed with a focus on clean architecture, maintainability, asynchronous processing, secure enterprise integration, and clear separation of business responsibilities.

## User Journey

The main customer flow is centered around connecting and analyzing the customer's banking accounts:

1. The customer enters the application and is presented with supported banks.
2. The customer selects the banks and accounts they want to connect to the application.
3. The application uses **Len APIs** to access the customer's authorized banking account data and transactions.
4. Accounts from the selected banks are displayed under their respective banks within the application.
5. Banking transactions from the customer's connected accounts are collected and processed.
6. The system analyzes the transactions and categorizes spending based on transaction information and matching rules.
7. The customer can view their transactions together with the resulting financial insights inside the application.

This integration provides a unified view of banking activity across multiple connected banks instead of requiring the customer to manage each bank separately.

## Financial Analysis & Spending Categorization

The backend processes banking transactions to generate useful financial insights for customers.

Transaction descriptions and related information are analyzed using **Regular Expressions** and business rules to identify spending patterns and assign transactions to meaningful categories, such as:

- Restaurants
- Cafés
- Other spending categories based on transaction data

The categorized data can then be used to provide customers with a clearer understanding of where their money is being spent.

## Financial Goals

The application also includes personal financial goal management.

Customers can create goals such as saving for a car by:

- Defining the target amount of the goal
- Tracking the amount accumulated toward the goal
- Viewing the percentage of progress toward the target
- Defining how much of their recurring monthly income should be allocated to the goal

The system uses incoming financial data to support the goal-tracking process and automatically account for the customer's configured goal contribution.

## Core Features

- Multi-bank account integration through **Len APIs**
- Retrieval and processing of authorized banking account data
- Banking transaction aggregation across multiple connected banks
- Transaction normalization and processing
- Spending analysis and categorization
- Rule-based transaction classification using Regular Expressions
- Account-level financial insights
- Personal financial goals and progress tracking
- Configurable recurring goal contributions
- RESTful API endpoints
- Asynchronous background processing
- Secure authentication and authorization
- Database persistence and data access abstraction
- Messaging-based communication for asynchronous workflows

## Architecture

The backend follows **Clean Architecture** principles with a clear separation between API, application/business logic, domain models, and infrastructure concerns.

The project also applies **CQRS** to separate read and write operations where appropriate, helping keep application use cases focused and maintainable.

Asynchronous workflows are supported through messaging, including **RabbitMQ**, to reduce coupling and improve the handling of transaction-processing workloads.

## Enterprise Authentication

The project also included **LDAP-based authentication** for bank employees.

Employees could authenticate using their existing corporate accounts configured within the bank's LDAP environment. The application validated users against the configured directory and user groups to control access to the system.

## Tech Stack

- **C#**
- **ASP.NET Core Web API**
- **Entity Framework Core**
- **SQL Server**
- **PostgreSQL**
- **Len APIs**
- **LDAP**
- **RabbitMQ**
- **Redis**
- **Clean Architecture**
- **CQRS**
- **JWT Authentication**
- **Repository / Unit of Work**
- **REST APIs**
- **Git / GitHub**

## My Role

**Backend .NET Developer**

My responsibilities focused on designing and implementing backend functionality, including:

- Developing RESTful APIs for banking-related operations
- Integrating **Len APIs** to retrieve customers' authorized banking accounts and transactions across multiple banks
- Implementing transaction aggregation and processing logic across connected bank accounts
- Implementing spending analysis and transaction categorization using Regular Expressions and business rules
- Developing account-level financial insights
- Implementing financial goal functionality, including progress tracking and recurring goal contributions
- Developing asynchronous transaction-processing workflows using RabbitMQ
- Implementing **LDAP-based authentication** for bank employees using their existing corporate directory accounts and configured user groups
- Applying Clean Architecture and CQRS patterns
- Working with Entity Framework Core and relational databases
- Implementing authentication and authorization mechanisms
- Contributing to reliable and maintainable backend business logic

## Engineering Focus

The project demonstrates practical experience in:

- Banking data integration
- Multi-bank transaction aggregation
- External API integration
- Financial data processing and analysis
- Rule-based transaction categorization
- Personal financial management features
- Asynchronous and message-driven processing
- Enterprise authentication and authorization
- Maintainable backend architecture
- Secure API design
- Scalable data access and processing

## Source Code

The project source code is private due to the nature of the banking project and its business requirements.

This repository serves as a high-level technical and portfolio overview of the project.
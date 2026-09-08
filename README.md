# Saudi Social Development Bank

A backend solution developed for a banking environment to support secure banking data integration, transaction processing, financial analysis, and personal financial management through reliable and asynchronous backend services.

> **Confidentiality Notice:** This README intentionally provides a high-level technical overview. Specific banking workflows, business rules, data structures, integration details, and internal implementation details are omitted due to confidentiality and security requirements.

## Overview

The project provides backend services for integrating authorized banking data from multiple financial institutions through an external banking integration service.

The system supports banking account integration, transaction aggregation, financial analysis, spending insights, and personal financial management features.

The architecture emphasizes maintainability, secure integration, separation of responsibilities, and asynchronous processing for background workloads.

## High-Level Workflow

At a high level, the system follows this flow:

**Account Linking → Banking Data Retrieval → Transaction Processing → Asynchronous Financial Analysis → Categorized Financial Insights**

After a customer successfully completes the account-linking process, the backend triggers the financial analysis workflow asynchronously. A dedicated background processing component handles the analysis so the customer-facing flow does not need to wait synchronously for the entire process.

The resulting financial insights become available in the application after processing is completed.

## Financial Analysis

The financial analysis component processes authorized banking transactions and extracts relevant transaction information to generate meaningful financial insights.

Transactions can be analyzed and organized into spending categories according to business-defined rules. The processed results are persisted and associated with the relevant customer, allowing the application to present categorized financial activity and spending insights.

Specific categorization rules, matching patterns, internal data models, and business logic are intentionally not documented publicly.

## Asynchronous Processing

The financial analysis workflow is handled asynchronously through **RabbitMQ** and a separate processing component.

The high-level flow is:

**Successful Account Linking → RabbitMQ Message → Financial Analysis Processing → Persist Results → Financial Insights Available in the Application**

This message-driven approach helps decouple the customer-facing backend from background financial-processing workloads and improves scalability and responsiveness.

## Financial Goals

The application also provides personal financial goal management as a separate feature.

Customers can create financial goals, define target amounts, and track their progress based on their financial activity.

The detailed business rules and internal calculations behind the feature are intentionally omitted from this public overview.

## Enterprise Authentication

The project included enterprise authentication for internal users through **LDAP** integration.

Authentication and authorization were implemented to integrate with the organization's existing enterprise identity environment while keeping access controlled according to the application's requirements.

Specific directory configuration, group names, authentication settings, and internal security details are intentionally excluded.

## Core Features

- Multi-bank account integration
- Authorized banking data retrieval
- Transaction aggregation and processing
- Financial transaction analysis
- Spending categorization and financial insights
- Asynchronous background processing
- Message-driven communication using RabbitMQ
- Personal financial goals
- RESTful API endpoints
- Authentication and authorization
- Enterprise LDAP integration
- Database persistence and data access abstraction

## Architecture

The backend follows **Clean Architecture** principles with separation between API, application/business logic, domain, and infrastructure concerns.

The project also applies **CQRS** to separate read and write operations where appropriate.

Asynchronous processing is implemented using **RabbitMQ**, with financial analysis handled independently from the customer-facing workflow.

This architecture helps reduce coupling, improve maintainability, and support scalable background processing.

## Tech Stack

- **C#**
- **ASP.NET Core Web API**
- **Entity Framework Core**
- **SQL Server**
- **PostgreSQL**
- **External Banking APIs**
- **RabbitMQ**
- **Redis**
- **LDAP**
- **Clean Architecture**
- **CQRS**
- **JWT Authentication**
- **Repository / Unit of Work**
- **REST APIs**
- **Git / GitHub**

## My Role

**Backend .NET Developer**

My responsibilities included:

- Developing RESTful APIs for banking-related operations
- Integrating external banking services
- Implementing account and transaction processing workflows
- Contributing to financial analysis and spending-insight functionality
- Developing asynchronous processing workflows using RabbitMQ
- Contributing to the integration with the dedicated financial-analysis component
- Implementing enterprise authentication through LDAP integration
- Applying Clean Architecture and CQRS patterns
- Working with Entity Framework Core and relational databases
- Implementing authentication and authorization mechanisms
- Contributing to reliable and maintainable backend business logic

## Engineering Focus

The project demonstrates practical experience in:

- Banking data integration
- External API integration
- Financial transaction processing
- Asynchronous and message-driven architecture
- Background processing
- Enterprise authentication
- Clean Architecture and CQRS
- Secure backend API design
- Scalable data access and processing

## Source Code

The project source code is private due to the nature of the banking project and its business and security requirements.

This repository serves as a high-level technical and portfolio overview without exposing confidential banking implementation details.
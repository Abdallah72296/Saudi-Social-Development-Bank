# Saudi Social Development Bank

A backend solution developed for the Saudi Social Development Bank to support multi-bank account integration, transaction aggregation, financial analysis, spending categorization, and personal financial management through reliable and asynchronous backend services.

## Overview

The project provides backend services that integrate with external banking data through **Len APIs**, allowing customers to link accounts from multiple banks and bring their banking activity into one application.

The system separates the account-linking experience from the financial analysis process. After successful account linking, the backend triggers financial analysis asynchronously through **RabbitMQ**, allowing the customer to continue using the application without waiting for the analysis to finish.

The project was designed with a focus on clean architecture, maintainability, secure enterprise integration, asynchronous processing, and clear separation of business responsibilities.

## User Journey

The main customer flow for banking data analysis works as follows:

1. The customer logs into the application.
2. The customer enters the account statement feature.
3. The customer selects the banks whose accounts they want to analyze.
4. The backend retrieves the customer's accounts for the selected banks and the transactions associated with those accounts.
5. The customer is shown a consent/report screen explaining that their financial data will be retrieved, displayed in the application, and analyzed according to business-defined conditions.
6. If the customer accepts, the application opens the external **Len** flow in a browser.
7. The customer reviews Len's terms and links/authorizes their bank accounts.
8. After successful linking, the customer receives a successful-linking confirmation.
9. The customer is redirected back to the application, where the application indicates that linking succeeded and financial analysis is in progress.
10. The backend publishes a message to **RabbitMQ** immediately after successful linking.
11. A separate **Financial Analysis** project consumes the message and starts processing the customer's banking data in the background.
12. After a short processing period, the analyzed transactions and categories become available to the customer in the application.

This asynchronous flow allows the account-linking process and financial analysis to remain decoupled and prevents the customer from having to wait synchronously for the complete analysis process.

## Financial Analysis & Transaction Categorization

The **Financial Analysis** process retrieves the customer's bank accounts and the transactions associated with each account, then analyzes the transactions individually.

The analysis extracts and evaluates information from each transaction, including details such as:

- Bank name
- Merchant / store name
- Transaction type, such as **Debit** or **Credit**
- Transaction description and related transaction information

Transactions are classified into spending categories using **Regular Expressions** and business-defined matching rules. Example categories include:

- Restaurants
- Cafés
- Hospitals
- Other categories derived from transaction data

The categorization process is not limited to a fixed list of categories. When transaction data represents a new category that is not already available, the system can add the new category so it can be presented to the customer.

The resulting analysis provides the customer with a categorized view of their financial activity, including the expenses associated with each category. The analyzed category and transaction data is persisted in the database and associated with the relevant customer.

## Asynchronous Financial Analysis

Financial analysis is handled as a background process in a separate **Financial Analysis** project.

The flow is:

**Successful Len Linking → RabbitMQ Message → Financial Analysis Consumer → Transaction Analysis → Categorization → Database Persistence → Categories & Transactions Available in the Application**

RabbitMQ is used as the messaging mechanism between the main backend flow and the financial analysis process. This keeps the user-facing request independent from the potentially heavier transaction-analysis workload.

The customer does not need to remain on a loading screen until analysis is completed. After returning from the linking flow, the application indicates that analysis is in progress, and the customer can access the resulting categories and transactions shortly afterward.

## Financial Goals

Financial Goals are a separate feature and are not part of the account-linking or financial-analysis flow.

Customers can independently create goals such as saving for a car by:

- Defining a target amount
- Tracking the accumulated amount toward the goal
- Viewing the percentage of progress toward the target
- Choosing how much of their recurring monthly incoming funds should be allocated toward the goal

The goal functionality uses the customer's financial data to support progress tracking and is managed independently from the background transaction-analysis workflow.

## Enterprise Authentication

The project also included **LDAP-based authentication** for bank employees.

Employees could authenticate using their existing corporate accounts configured within the bank's LDAP environment. The application validated users against the configured directory and user groups to control access to the system.

## Core Features

- Multi-bank account integration through **Len APIs**
- Customer account and transaction retrieval
- External bank account linking flow
- Banking transaction aggregation across multiple connected accounts
- Transaction analysis and processing
- Debit / Credit identification
- Bank and merchant information extraction
- Rule-based transaction categorization using Regular Expressions
- Dynamic category creation based on transaction data
- Category-level expense aggregation and insights
- Asynchronous financial analysis using RabbitMQ
- Separate Financial Analysis processing service
- Personal financial goals and progress tracking
- Configurable recurring goal contributions
- RESTful API endpoints
- Secure authentication and authorization
- LDAP-based enterprise authentication
- Database persistence and data access abstraction

## Architecture

The backend follows **Clean Architecture** principles with a clear separation between API, application/business logic, domain models, and infrastructure concerns.

The project also applies **CQRS** to separate read and write operations where appropriate, helping keep application use cases focused and maintainable.

The financial-analysis workflow uses **message-driven asynchronous processing** through RabbitMQ. The main backend publishes an event/message after successful account linking, while the separate Financial Analysis project consumes the message and performs the analysis in the background.

This approach reduces coupling between the customer-facing workflow and transaction-processing workloads.

## Tech Stack

- **C#**
- **ASP.NET Core Web API**
- **Entity Framework Core**
- **SQL Server**
- **PostgreSQL**
- **Len APIs**
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

My responsibilities focused on designing and implementing backend functionality, including:

- Developing RESTful APIs for banking-related operations
- Integrating **Len APIs** for customer bank account linking and retrieval of authorized banking data
- Implementing account and transaction aggregation across multiple connected banks
- Implementing transaction analysis and extracting bank, merchant, and Debit/Credit information
- Implementing spending categorization using Regular Expressions and business rules
- Supporting dynamic category creation based on transaction data
- Implementing category-level expense aggregation and financial insights
- Developing the asynchronous workflow that publishes analysis messages through RabbitMQ after successful account linking
- Contributing to the integration with the separate Financial Analysis processing service
- Implementing **LDAP-based authentication** for bank employees using their existing corporate directory accounts and configured user groups
- Applying Clean Architecture and CQRS patterns
- Working with Entity Framework Core and relational databases
- Implementing authentication and authorization mechanisms
- Contributing to reliable and maintainable backend business logic

## Engineering Focus

The project demonstrates practical experience in:

- Banking data integration
- Multi-bank account and transaction aggregation
- External API integration through Len
- Financial transaction processing and analysis
- Rule-based transaction categorization
- Dynamic financial categories
- Category-level spending insights
- Asynchronous and message-driven processing with RabbitMQ
- Separation of customer-facing APIs from background financial analysis
- Enterprise authentication and authorization
- Clean Architecture and CQRS
- Secure and maintainable backend API design

## Source Code

The project source code is private due to the nature of the banking project and its business requirements.

This repository serves as a high-level technical and portfolio overview of the project.
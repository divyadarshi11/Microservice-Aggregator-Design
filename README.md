# Microservice Aggregator Design
This project demonstrates the Aggregator Design Pattern applied in a Microservices Architecture. The goal is to break down complex business logic into smaller, independently deployable services, and then aggregate the data from these services into a unified response using an aggregator service.

## Services
### Account Service

Purpose:
Manages the creation and retrieval of bank accounts.

Functionality:
Creates a new bank account with a specified name and initial balance.
Retrieves details of an existing account.

### Fund Transfer Service

Purpose: Manages the transfer of funds between accounts.

Functionality:
Transfers money between two bank accounts.
Retrieves information about the status of a specific fund transfer.

### Report Service (Aggregator)

Purpose: Aggregates data from both the Account Service and Fund Transfer Service.

Functionality:
Collects account details and the status of recent transfers.
Combines the data and sends the unified response to the client.

## Prerequisites
JDK: Java Development Kit (JDK) 8 or higher

Maven: Dependency management and build tool

H2 Console: For accessing and managing the H2 database via a web browser (optional)

## Steps to Run and Test the Services
##### 1. Run the All Services
##### 2. Test and Connect to H2 Databases
   
#### Account Service DB:

   Open the H2 Console at http://localhost:8080/h2-console.

   Use the following connection details:
   
   JDBC URL: jdbc:h2:mem:AccountService_DB
   
   Username: sa
   
   Password: (leave blank)
   
   Click "Connect" to access the Account Service database.

#### Fund Transfer Service DB:

  Open the H2 Console at http://localhost:8081/h2-console.
  
  Use the following connection details:
  
  JDBC URL: jdbc:h2:mem:FundTransfer_DB
  
  Username: sa
  
  Password: (leave blank)
  
  Click "Connect" to access the Fund Transfer Service database.

##### 3. Test the Aggregator Service
   
To test the Aggregator Service, open your browser or API tool (like Postman) and call the following endpoint:

http://localhost:8082/banking/report/getTxnDetails/{account number}

This will fetch the aggregated transaction details for the specified account ID

## C4 Diagram : 
The C4 Model is a hierarchical approach for visualizing and documenting software architecture. It was created by Simon Brown to help developers, architects, and stakeholders understand the structure of software systems at different levels of detail.

**C4 stands for:**

* **Context** : Show the system in its broader context , including users , external systems , and high-level goals.
* **Container** : Decomposes the system software into containers or application to be run . Captures the high level technology choices and components.
* **Component**: Depicts the individual components within each container , detailing their specific responsibilites.
* **Code**: Can be used to zoom into specific components and showcase their internal structure or implementation details. This uses class diagram.
* Each level provides a different view of the system, from high-level overview to detailed implementation.

| Level   | Name      | Description                     | Audience               |
| ------- | --------- | ------------------------------- | ---------------------- |
| Level 1 | Context   | System and external interaction | Everyone               |
| Level 2 | Container | Applications and databases      | Developers, Architects |
| Level 3 | Component | Internal components             | Developers             |
| Level 4 | Code      | Classes and code                | Developers             |



## Context Diagram:

```mermaid
C4Context
title Internet Banking System - System Context Diagram

Enterprise_Boundary(bank, "Bank Enterprise") {

    Person(customer, "Bank Customer", "A customer who uses internet banking to manage accounts, transfer money, and view transactions")

    Person(admin, "Bank Administrator", "Manages system, monitors transactions, and maintains customer accounts")

    System(bankSystem, "Internet Banking System", "Provides banking services such as account management, fund transfer, and transaction history")

}

System_Ext(emailSystem, "Email System", "External system used to send notifications and alerts")

System_Ext(paymentGateway, "Payment Gateway", "Processes online payments and fund transfers securely")

System_Ext(coreBanking, "Core Banking System", "Main banking system that stores account and transaction data")

System_Ext(mobileApp, "Mobile Banking App", "Mobile application used by customers to access banking services")

Rel(customer, bankSystem, "Uses", "HTTPS")
Rel(admin, bankSystem, "Manages and monitors", "HTTPS")

Rel(bankSystem, emailSystem, "Sends email notifications", "SMTP")
Rel(bankSystem, paymentGateway, "Processes payments", "HTTPS")
Rel(bankSystem, coreBanking, "Reads/Writes account data", "Secure API")
Rel(mobileApp, bankSystem, "Uses", "HTTPS")
```

## Container Diagram: 
```mermaid
C4Container
title Internet Banking System - Container Diagram

Person(customer, "Bank Customer", "Uses web or mobile app to access banking services")
Person(admin, "Bank Administrator", "Manages and monitors the banking system")

System_Boundary(bankSystem, "Internet Banking System") {

    Container(webApp, "Web Application", "React, HTML, CSS, JavaScript", "Allows customers to access banking services through web browser")

    Container(mobileApp, "Mobile Application", "Android / iOS", "Allows customers to access banking services through mobile devices")

    Container(apiApp, "Backend API", "Java, Spring Boot", "Handles business logic, authentication, and processes requests")

    Container(authService, "Authentication Service", "Spring Security, JWT", "Provides user authentication and authorization")

    ContainerDb(database, "Banking Database", "MySQL", "Stores customer accounts, transactions, and user data")

}

System_Ext(emailSystem, "Email System", "Sends email notifications")
System_Ext(paymentGateway, "Payment Gateway", "Processes online payments")

Rel(customer, webApp, "Uses", "HTTPS")
Rel(customer, mobileApp, "Uses", "HTTPS")

Rel(admin, webApp, "Manages system", "HTTPS")

Rel(webApp, apiApp, "Sends requests", "REST API")
Rel(mobileApp, apiApp, "Sends requests", "REST API")

Rel(apiApp, authService, "Authenticates users", "JWT")
Rel(apiApp, database, "Reads/Writes data", "SQL")

Rel(apiApp, emailSystem, "Sends notifications", "SMTP")
Rel(apiApp, paymentGateway, "Processes payments", "HTTPS")
```

## Component Diagram: 
A Component Diagram is a structural diagram that illustrates the organization and relationships between software components, their interfaces, and dependencies within a system.

```mermaid
C4Component
title Internet Banking System - Component Diagram

Person(customer, "Bank Customer", "Uses internet banking services")

Container(apiApp, "Backend API", "Spring Boot", "Handles all banking operations")

ContainerDb(database, "Banking Database", "MySQL", "Stores user and transaction data")

System_Ext(emailSystem, "Email System", "Sends notifications")
System_Ext(paymentGateway, "Payment Gateway", "Processes payments")

Component(authComponent, "Authentication Component", "Spring Security", "Handles login, logout, and user authentication")

Component(accountComponent, "Account Management Component", "Java", "Manages bank accounts and balances")

Component(transactionComponent, "Transaction Component", "Java", "Handles fund transfers and transaction history")

Component(notificationComponent, "Notification Component", "Java", "Sends email notifications")

Component(userComponent, "User Management Component", "Java", "Manages user profile and registration")

Rel(customer, authComponent, "Logs in", "HTTPS")

Rel(authComponent, database, "Reads/Writes user credentials", "SQL")

Rel(accountComponent, database, "Reads account data", "SQL")

Rel(transactionComponent, database, "Stores transaction data", "SQL")

Rel(transactionComponent, paymentGateway, "Processes payment", "HTTPS")

Rel(notificationComponent, emailSystem, "Sends email", "SMTP")

Rel(userComponent, database, "Stores user information", "SQL")

Rel(apiApp, authComponent, "Uses")
Rel(apiApp, accountComponent, "Uses")
Rel(apiApp, transactionComponent, "Uses")
Rel(apiApp, notificationComponent, "Uses")
Rel(apiApp, userComponent, "Uses")
```
The Component Diagram shows the internal structure of the Backend API container. It illustrates the major components such as Authentication, User Management, Account Management, Transaction, and Notification components. These components interact with the database and external systems like Payment Gateway and Email System to perform banking operations securely and efficiently.

## Code Diagram:
A Code Diagram represents the internal implementation of a component by showing classes, interfaces, attributes, methods, and their relationships. It helps developers understand how the system is implemented at the code level.

```mermaid
classDiagram

class User {
    +int userId
    +String name
    +String email
    +String password
    +login()
    +logout()
}

class Account {
    +int accountNumber
    +double balance
    +deposit()
    +withdraw()
    +checkBalance()
}

class Transaction {
    +int transactionId
    +double amount
    +String type
    +transfer()
    +getTransactionHistory()
}

class AuthenticationService {
    +login()
    +logout()
    +validateUser()
}

class NotificationService {
    +sendEmail()
    +sendSMS()
}

User --> Account : owns
Account --> Transaction : records
AuthenticationService --> User : authenticates
Transaction --> NotificationService : sends notification
```
The Code Diagram provides a detailed view of the system implementation. It shows classes, methods, and relationships, helping developers understand how the system works internally.


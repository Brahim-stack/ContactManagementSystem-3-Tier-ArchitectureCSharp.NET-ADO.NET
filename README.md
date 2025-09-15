# Contact Management System - 3-Tier Architecture

A comprehensive contact management application built using C# and SQL Server, demonstrating clean 3-tier architecture principles.

## 🏗️ Architecture Overview

### 1. **Presentation Layer** (`ContactsConsoleApp`)
- User interface through console application
- Handles user input and displays results
- Communicates only with the Business Layer

### 2. **Business Layer** (`ContactsBusinessLayer`)
- Contains business logic and validation
- Implements the `clsContact` class with CRUD operations
- Manages object state (Add/Update modes)
- Acts as intermediary between Presentation and Data layers

### 3. **Data Access Layer** (`ContactsDataAccessLayer`)
- Direct database communication using ADO.NET
- Implements parameterized queries for security
- Handles connection management and data retrieval
- Returns data to Business Layer

## 🚀 Features

- **Create** new contacts with personal information
- **Read** contact details by ID
- **Update** existing contact information
- **Delete** contacts from the system
- **List** all contacts in the database
- Proper null handling for optional fields (ImagePath)
- SQL injection prevention through parameterized queries

## 💻 Technologies Used

- C# (.NET Framework)
- SQL Server
- ADO.NET for database connectivity
- 3-Tier Architecture Pattern

## 📋 Prerequisites

- Visual Studio (2019 or later recommended)
- SQL Server (Express edition or higher)
- .NET Framework 4.x

## 🔧 Setup Instructions

1. Clone this repository
2. Create a SQL Server database named `ContactsDB`
3. Run the following SQL script to create the Contacts table:
```sql
CREATE TABLE Contacts (
    ContactID INT IDENTITY(1,1) PRIMARY KEY,
    FirstName NVARCHAR(50) NOT NULL,
    LastName NVARCHAR(50) NOT NULL,
    Email NVARCHAR(100),
    Phone NVARCHAR(20),
    Address NVARCHAR(200),
    DateOfBirth DATETIME,
    CountryID INT,
    ImagePath NVARCHAR(500)
);

# Project1Adonet

**Project1Adonet** is a Windows Forms application designed to manage customer and city information using ADO.NET for database operations. This project demonstrates basic CRUD (Create, Read, Update, Delete) functionality and how to handle SQL Server database connections effectively in a C# application.

---

## Features

### **Customer Management (`FrmCustomer`)**
1. **List Customers**
   - Displays a list of customers, including their associated city details.
   - Uses a SQL `INNER JOIN` to fetch city names from the `TblCity` table.

2. **Add Customer**
   - Allows adding new customers to the `TblCustomer` table.
   - Requires details like name, surname, city, balance, and status (active or passive).

3. **Update Customer**
   - Updates existing customer information based on the `CustomerId`.

4. **Delete Customer**
   - Deletes a customer record using the `CustomerId`.

5. **Search Customer**
   - Searches for customers by name and displays the result in a grid.

6. **Stored Procedure Execution**
   - Demonstrates the execution of a stored procedure `CustomerListWithCity` to retrieve customer data.

---

### **City Management (`FrmCity`)**
1. **List Cities**
   - Displays a list of all cities from the `TblCity` table.

2. **Add City**
   - Adds new cities with their country details.

3. **Update City**
   - Updates existing city information based on the `CityId`.

4. **Delete City**
   - Deletes a city record using the `CityId`.

5. **Search City**
   - Searches for cities by name and displays the result in a grid.

---

### **Navigation (`FrmMap`)**
- Acts as a central navigation form.
- Allows switching between the `FrmCustomer` and `FrmCity` forms.

---

## Database Structure

### Tables
1. **`TblCustomer`**
   - `CustomerId`: Primary Key (int)
   - `CustomerName`: Customer's First Name (nvarchar)
   - `CustomerSurname`: Customer's Last Name (nvarchar)
   - `CustomerCity`: Foreign Key referencing `TblCity.CityId` (int)
   - `CustomerBalance`: Customer's Balance (decimal)
   - `CustomerStatus`: Active/Passive Status (bit)

2. **`TblCity`**
   - `CityId`: Primary Key (int)
   - `CityName`: Name of the City (nvarchar)
   - `CityCountry`: Name of the Country (nvarchar)

### Stored Procedures
- **`CustomerListWithCity`**
  - Retrieves customer details along with their city names.

---

## Prerequisites

1. **SQL Server**
   - Ensure a SQL Server instance is running, and the database `DbCustomer` is created with the appropriate tables and stored procedures.

2. **.NET Framework**
   - Requires .NET Framework version 4.5 or higher.

3. **Visual Studio**
   - The project is designed to be run using Visual Studio.

---

## Setup

1. Clone the repository or download the project files.
2. Open the solution file (`Project1Adonet.sln`) in Visual Studio.
3. Restore NuGet packages if required.
4. Update the connection string in the `SqlConnection` object to match your SQL Server instance:
   ```csharp
   SqlConnection sqlConnection = new SqlConnection("Server=YOUR_SERVER;initial catalog=DbCustomer;integrated security=true");
   ```
5. Build the project and run it.

---

## Usage

1. **Launch the application** using `FrmMap`.
2. **Navigate to forms**:
   - Open `FrmCustomer` for customer operations.
   - Open `FrmCity` for city operations.
3. Perform actions like adding, updating, deleting, and searching records.

---

## Error Handling

- Exceptions related to SQL or application logic are displayed using `MessageBox` dialogs.
- Ensure input validation is performed to prevent invalid data.

---

## Future Improvements

1. Implement better input validation to handle edge cases.
2. Add user authentication for secure access.
3. Use Entity Framework for better maintainability.
4. Improve UI design for enhanced user experience.

---

#


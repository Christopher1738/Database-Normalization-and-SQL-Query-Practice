Database Normalization Assignment - SQL Implementation Guide

This project demonstrates database normalization techniques to transform data into 1NF and 2NF. The solution is contained in answers.sql and can be executed in any standard SQL environment.

PREREQUISITES
- MySQL 8.0+ or compatible database system
- MySQL Workbench or command-line client
- Basic SQL knowledge

INSTALLATION & EXECUTION

1. Using MySQL Workbench:
   - Connect to your database server
   - Open a new SQL tab (File > New Query Tab)
   - Copy all content from answers.sql
   - Paste into the query window
   - Execute the entire script (lightning bolt icon or Ctrl+Shift+Enter)

2. Using Command Line:
   mysql -u [username] -p[password] [database_name] < answers.sql

STRUCTURE OVERVIEW

The script performs these operations in sequence:

1. QUESTION 1 SOLUTION (1NF Normalization)
   - Creates OrderDetails_1NF table
   - Inserts normalized data with atomic values
   - Verification query included

2. QUESTION 2 SOLUTION (2NF Normalization)
   - Creates two normalized tables:
     * Orders (order information)
     * OrderItems (product details)
   - Establishes proper foreign key relationship
   - Verification queries for both tables

EXPECTED RESULTS

After successful execution:
- OrderDetails_1NF will contain 6 records (1 per product)
- Orders will contain 3 records (1 per customer order)
- OrderItems will contain 6 records (product quantities)

TROUBLESHOOTING

Common issues and solutions:
1. Table already exists errors:
   - Modify table names in the SQL file
   - Or run: DROP TABLE IF EXISTS OrderDetails_1NF, Orders, OrderItems;

2. Permission errors:
   - Verify your database user has CREATE privileges
   - Contact your DBA if needed

3. Syntax errors:
   - Check your database version compatibility
   - For MySQL, ensure you're using version 8.0+

DATABASE SCHEMA DETAILS

Final table structure:
- Orders (OrderID PK, CustomerName)
- OrderItems (OrderItemID PK, OrderID FK, Product, Quantity)

The normalization process:
1. Achieves 1NF by eliminating multi-value attributes
2. Achieves 2NF by removing partial dependencies

TESTING VERIFICATION

To manually verify the results:
1. Check row counts match expectations
2. Confirm no customer names are duplicated
3. Verify all product quantities are preserved

For questions or issues, please contact the repository maintainer.

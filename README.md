# E-Commerce-Retail-SQL_Case_Study

1.1	Database Overview
   This case study is based on five datasets:
1.	Customers (500 records) – Contains customer details such as name, email, gender, age, country, and signup date.
2.	Products (50 records) – Includes product details such as name, category, brand, and price.
3.	Orders (1,200 records) – Stores order transactions, including customer purchases, total amount, order status, and payment method.
4.	Order Details (1,500 records) – Contains product-level details of each order, including quantity and unit price.
5.	Returns (150 records) – Stores return information including reason, status, and date of return.
These datasets are linked through:
•	CustomerID (to associate orders with customers)
•	OrderID (to connect orders with order details and returns)
•	ProductID (to associate order details with products)





2. Database Schema Design:


1.1 Database Overview 
This case study is based on  ive datasets: 
1. Customers (500 records) – Contains customer details such as name, email, 
gender, age, country, and signup date. 
2. Products (50 records) – Includes product details such as name, category, brand, 
and price. 
3. Orders (1,200 records) – Stores order transactions, including customer 
purchases, total amount, order status, and payment method. 
4. Order Details (1,500 records) – Contains product-level details of each order, 
including quantity and unit price. 
5. Returns (150 records) – Stores return information including reason, status, and 
date of return. 
These datasets are linked through: 
 CustomerID (to associate orders with customers) 
 OrderID (to connect orders with order details and returns) 
 ProductID (to associate order details with products) 
2. Database Schema Design: 
2.1  Customers Table :- 
 
Column Name Data Type Description 
CustomerID INT Unique identifier for customer 
Name TEXT Full name of the customer 
Email TEXT Customer's email address 
Gender TEXT Male / Female 
Age INT Age of the customer 
Country TEXT Country of residence 
SignupDate DATE Date when customer registered 
 
 
2.2 Orders Table :- 
 
Column 
Name 
Data 
Type 
Description 
OrderID INT Unique identi ier for the 
order 
Customer ID INT References customers_500 
Order Date DATE Date the order was placed 
Total Amount DECIMAL Total value of the order 
Payment Method TEXT UPI / Credit Card / Net 
Banking etc. 
Order Status TEXT Delivered / Returned / 
Cancelled 
 
 
 
 
 
 
 
 
2.3 Order_details Table 
Column Name Data Type Description 
OrderDetailID INT Unique identi ier for the line item 
OrderID INT References orders_expanded 
ProductID INT References products_expanded 
Quantity INT Quantity of product ordered 
UnitPrice DECIMAL Price per unit at the time of 
order 
 
2.4 Products Table 
 
Column Name Data Type Description 
ProductID INT Unique product ID 
ProductName TEXT Name of the product 
Category TEXT Electronics / Beauty / Fashion 
Brand TEXT Brand name 
Price INT Retail price of the product 
 
2.5 Returns Table 
 
Column 
Name 
Data 
Type 
Description 
ReturnID INT Unique return ID 
OrderID INT References orders_expanded 
ReturnDate DATE Date return was made 
Reason TEXT Reason for return (Damaged, Late, 
etc.) 
Status TEXT Return status (Approved / Pending 
/ Rejected) 
 
 
 
 
 
3.Data Processing:- 
 Check for null or missing values and handle them appropriately. 
 Validate data types to match the expected format. 
 Ensure foreign key integrity between tables. 
 Remove duplicate records if any exist. 
 Normalize data to improve ef iciency and avoid redundancy. 
 Removed duplicate rows using DISTINCT or row ID check

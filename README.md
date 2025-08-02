## E-commerce SQL Case Study: Customer, Product, and Order Analytics
  This project showcases an end-to-end SQL-based analysis of an e-commerce retail database, focused on extracting actionable insights from customer behavior, product sales, order trends, and returns. It demonstrates how SQL can be used for data cleaning, query writing, KPI extraction, and business-driven decision-making.

## Dataset Overview
The case study is built on 5 relational datasets:
| Table Name       | Records | Description                                                                    |
|------------------|---------|--------------------------------------------------------------------------------|
| `Customers`      | 500     | Contains customer details: name, email, age, gender, country, and signup date. |
| `Products`       | 50      | Includes product information like name, category, brand, and price.            |
| `Orders`         | 1,200   | Stores customer orders: date, total amount, status, and payment method.        |
| `Order_Details`  | 1,500   | Line-item breakdown of each order with quantity and unit price.                |
| `Returns`        | 150     | Information about returned orders including reason, status, and date.          |


## Customers Table

| Column Name | Data Type | Description                  |
|-------------|-----------|------------------------------|
| CustomerID  | INT       | Unique customer ID           |
| Name        | TEXT      | Customer’s full name         |
| Email       | TEXT      | Email address                |
| Gender      | TEXT      | Gender (Male / Female)       |
| Age         | INT       | Customer’s age               |
| Country     | TEXT      | Country of residence         |
| SignupDate  | DATE      | Date of registration         |

## Products Table

| Column Name  | Data Type | Description                        |
|--------------|-----------|------------------------------------|
| ProductID    | INT       | Unique product ID                  |
| ProductName  | TEXT      | Name of the product                |
| Category     | TEXT      | Product category (Electronics, etc.) |
| Brand        | TEXT      | Brand name                         |
| Price        | INT       | Retail price                       |


## Orders Table

| Column Name    | Data Type | Description                        |
|----------------|-----------|------------------------------------|
| OrderID        | INT       | Unique order ID                    |
| CustomerID     | INT       | Foreign key to Customers table     |
| OrderDate      | DATE      | Date the order was placed          |
| TotalAmount    | DECIMAL   | Total value of the order           |
| PaymentMethod  | TEXT      | UPI, Credit Card, Net Banking, etc.|
| OrderStatus    | TEXT      | Delivered, Returned, Cancelled     |

## Order_Details Table

| Column Name   | Data Type | Description                           |
|---------------|-----------|---------------------------------------|
| OrderDetailID | INT       | Unique identifier for the line item   |
| OrderID       | INT       | Foreign key to Orders table           |
| ProductID     | INT       | Foreign key to Products table         |
| Quantity      | INT       | Quantity of product ordered           |
| UnitPrice     | DECIMAL   | Price per unit at time of order       |

## Returns Table

| Column Name | Data Type | Description                                   |
|-------------|-----------|-----------------------------------------------|
| ReturnID    | INT       | Unique return ID                              |
| OrderID     | INT       | Foreign key to Orders table                   |
| ReturnDate  | DATE      | Date of return                                |
| Reason      | TEXT      | Reason (Damaged, Late, etc.)                  |
| Status      | TEXT      | Return status (Approved, Pending, Rejected)   |




## Relationships:

CustomerID connects Customers ↔ Orders
OrderID connects Orders ↔ Order_Details ↔ Returns
ProductID connects Products ↔ Order_Details

## Data Preprocessing Steps

Checked for nulls and duplicates
Validated foreign key relationships
Normalized tables for efficiency
Ensured accurate data types and referential integrity

## SQL Query Highlights

#### Basic-Level:
Customer location, age, and signup trends
Product filtering by category and price
Total revenue and unique brand/category stats
Orders by amount, status, or recent date

# Intermediate-Level:
Top 5 customers by total spending
Monthly return volume and product-level revenue
Products never returned
Orders per customer, category performance, and ARPU

# Advanced-Level:
Customers with 50%+ return rate
Signup-to-first-order time analysis
Stored procedures:
GetCustomerSummary(customer_id)
TopSellingProducts(N)
MonthlyRevenueReport(year)
ProductRevenueByDateRange(start, end)
HighReturnCustomers(N)

## Key Business Insights

Customer Segmentation: Identified high-spending users and return-prone customers
Product Performance: Top-selling vs. underperforming items across categories
Sales Trends: Peak sales in festive seasons and high UPI/NetBanking usage
Inventory Flags: Low-stock, slow-moving products highlighted
Revenue Optimization: Electronics and Fashion drive over 60% of revenue

## Conclusion and Recommendations
# Summary
This project demonstrates how MySQL can be used to analyze retail sales data and customer behavior. The structured approach enables data-driven decision-making for business growth.

## Recommendations
Focus marketing efforts on high-value customers.
Increase stock for best-selling products.
Offer discounts on slow-moving products.
Engage with customers who have not made recent purchases.
Optimize inventory based on seasonal trends.

## Future Scope
# This study can be extended by:
Implementing predictive analytics using machine learning.
Integrating real-time dashboards with Power BI or Tableau.
Expanding the dataset with additional customer demographics for deeper analysis.


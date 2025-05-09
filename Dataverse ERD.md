### **Dataverse Schema for Inventory Management System (IMS)**

### **Overview**
This document outlines the **Dataverse schema** for the **Inventory Management System (IMS)** used by the manufacturing company. The schema includes core **tables (entities), relationships, and key fields** to support efficient order and inventory management.

---

### **Core Tables (Entities) & Fields**

### **1️⃣ Products (Inventory Items)**
Stores details of all products in stock.
| Field Name | Data Type | Description |
|------------|----------|-------------|
| Product ID | Unique Identifier | Primary Key |
| Product Name | Text | Name of the product |
| Category | Choice | Raw Materials, Finished Goods, etc.. |
| SKU | Text | Stock Keeping Unit |
| Supplier ID | Lookup (Suppliers) | Links to Supplier Table |
| Unit of Measurement | Choice | kg, pieces, liters, etc. |
| Reorder Level | Number | Threshold for reordering |
| Current Stock Quantity | Number | Available stock count |
| Unit Price | Currency | Price per unit |

### **2️⃣ Customer**
Information about Customers
| Field Name | Data Type | Description |
|------------|----------|-------------|
| Customer ID | Unique Identifier | Primary Key |
| Customer Last Name | Text | Last Name of the customer |
| Customer First Name | Text | First Name of the customer |
| Created on | Date and Time | Date of Customer Cretion |
| Customer Phone Number | Phone Number | Phone Number of the customer |
| Customer Email | Text | Email of the customer |
| Customer City | Text | City of the customer |
| Customer State | Text | State of the customer |
| Customer Country | Text | Country of the customer |


### **3️⃣ Customer Orders**
Tracks customer purchases and fulfillment status.
| Field Name | Data Type | Description |
|------------|----------|-------------|
| Order ID | Unique Identifier | Primary Key |
| Customer Name | Text | Name of the customer |
| Customer ID | Lookup (Customer Details) | Links to Customer Table |
| Product Name | Lookup (Product) | Links to Product Table |
| Order Date | Date/Time | Date order was placed |
| Order Status | Choice | Pending, Shipped, Delivered, Canceled |
| Total Order Value | Currency | Order amount |
| Payment Status | Choice | Paid, Unpaid, Partially Paid |
| Delivery Address | Text | Shipping location |

### **4️⃣ Inventory Transactions (Stock Movement)**
Records stock changes due to orders, restocking, or adjustments.
| Field Name | Data Type | Description |
|------------|----------|-------------|
| Transaction ID | Unique Identifier | Primary Key |
| Transaction Type | Choice | Stock-In, Stock-Out, Adjustment |
| Product ID | Lookup (Products) | Links to Product Table |
| Quantity Adjusted | Number | Amount of stock added/removed |
| Date & Time | Date/Time | When the transaction occurred |
| Reason for Adjustment | Choice | Damaged, Expired, Returned, etc. |
| Handled By | Lookup (Users) | Staff responsible for Order Request |

### **5 Suppliers & Vendors**
Maintains supplier details for procurement and restocking.
| Field Name | Data Type | Description |
|------------|----------|-------------|
| Supplier ID | Unique Identifier | Primary Key |
| Supplier Name | Text | Name of the supplier |
| Contact Information | Text | Phone |
| Contact Information | Text | Email |
| Products Supplied | Lookup (Products) | Links to Product Table |
| Payment Terms | Choice | Upfront Payment conditions before delivery date (30% 60%). |
| Last Order Date | Date/Time | Most recent transaction date |


---

## **Relationships Between Tables**
- **Products ↔ Suppliers** (One-to-Many) → Each supplier provides multiple products.
- **Customer Orders ↔ Products** (Many-to-Many) → An order can have multiple products, and a product can appear in multiple orders.
- **Inventory Transactions ↔ Products** (Many-to-One) → Each transaction is linked to a product.
- **Users ↔ Inventory Transactions** (Many-to-One) → Each transaction is recorded by a user.

---
![IMS](https://github.com/user-attachments/assets/b9ef417f-76ee-4a16-aec7-43fafbdc9d94)

---



## **Conclusion**
This Dataverse schema provides a **structured, secure, and scalable** database design for the Inventory Management System, ensuring smooth operations, automation, and analytics integration.

[Dataverse ERD Presentation](https://easynig-my.sharepoint.com/:p:/g/personal/sodiq_easynig_onmicrosoft_com/ETjfp14ImYFCj8YbBtvxbAABdtFtDiS4EssRY8q6yc9KqA?e=hzqiQh) is a powerpoint file for more insight of this sales pitch 


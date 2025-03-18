# Team 9 Mist 4610 Group Project 1

# Team Name
Group 9

# Problem Description

# Data Model
![Datamodel](https://github.com/agd0221/MIST4610Project/blob/main/Image%203-18-25%20at%2011.46%20AM.jpeg)
This data model is based off of a "fake" local Athens Coffee Shop and shows the relationships between different entities that we will need to use in our store.

The Customers entity represents the people that give the coffee shop business by making purchases; they are at the heart of the business. Customers have the attributes name, email, and phone number. Each customer can place multiple orders, establishing a one-to-many relationship between Customers and Orders.

The Orders entity records all purchases made by customers, detailing the attributes total amount, order date, and the payment method used. Orders are linked to OrderDetails, which breaks down each order into individual line items. Since an order consists of multiple items and each item can be part of multiple orders, there is a many-to-many relationship between Orders and MenuItems, resolved through the OrderDetails associative entity.

The MenuItems table represents all the food and drink options available. Each item has the attributes name, category (e.g., coffee, sandwich), price, and availability status. These items are also linked to the Inventory entity, which keeps track of how much we have in stock. Since each item in the menu has a supplier that provides it, there is a many-to-one relationship between Inventory and Suppliers, where each supplier can provide multiple inventory items, but a menu item can only have one supplier. The Suppliers entity stores the details of vendors that supply ingredients and goods to the coffee shop. It includes the attribiutes supplier names, contact information, and the type of supplies they provide.

The coffee shop also has employees who make the orders happen and manage overall operations. The Employees entity keeps track of employee attributes including name, role, salary, and hire date. Employees are responsible for processing orders, creating a one-to-many relationship between Employees and Orders. Additionally, employee work schedules are stored in the EmployeeSchedule table, which maintains records of shift start and end times.

To improve the coffee shop and get feedback, the business collects CustomerFeedback, where customers can rate their experience and leave comments on their orders. Each feedback entry is linked to both a customer and a specific order, establishing relationships between CustomerFeedback, Customers, and Orders.

The coffee shop also offers Discounts on certain orders, with the attributes discount percentage, description, and validity period. Each discount is applied to an order, forming a one-to-many relationship between Orders and Discounts.

Finally, the Payments table records financial transactions, including payment methods, amounts, and dates. Since each order results in a payment transaction, there is a one-to-one relationship between Orders and Payments

# Data Dictionary


# Queries

# Database Information
Name of the database: al_Group_47114_G9

# ChatGPT Use

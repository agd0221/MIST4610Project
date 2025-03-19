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

Finally, the Payments table records financial transactions, including payment methods, amounts, and dates. Since each order results in a payment transaction, there is a one-to-one relationship between Orders and Payments.

I would also like to mention that the dashed lines indicate a non-identifying relationship which means that the child entity can exist independently of the parent entity. In contrast, the solid black lines indicate a idetnifying relationship which shows that the child can't exist independently from the parent entity.

# Data Dictionary


# Queries
Query 1:
Query 1 retrieves a list of all employees, displaying their EmployeeID, Name, and Role. It directly pulls the necessary information from the Employees table without any joins or filters.

<img width="415" alt="image" src="https://github.com/user-attachments/assets/73e31f53-99e8-4c1e-a7b4-6a5452c1de1d" />

This query is useful for managers and HR teams who need a quick overview of all employees within the organization, along with their roles. It can serve as a foundation for more detailed employee reports, such as identifying specific roles within departments, tracking employee performance, or even managing schedules.

Query 2:
Query 2 lists the quantity of each inventory item along with the name of the supplier that provides the item where the quantity in stock is below 100 units. The results are ordered in ascending order based on quantity, showing the items with the lowest stock first.
![image](https://github.com/user-attachments/assets/649a7dd3-fa04-49dd-8814-a9e663ee0a35)
Query 2 allows managers to quickly identify which inventory items are running low and which suppliers provide these items. By focusing on items with quantities below 100, managers can prioritize reordering essential ingredients, beverages, or supplies before they run out. Listing the results in ascending order based on quantity makes it easier to spot the most critically low items first, allowing for timely restocking and smooth coffee shop operations. 

Query 3:
Query 3 lists each menu item along with the total quantity of that item ordered across all orders. It joins the MenuItems and OrderDetails tables to calculate the total quantity ordered for each item, groups the results by item, and orders them in descending order based on the total quantity ordered.
![image](https://github.com/user-attachments/assets/e6b22d11-dd3b-407a-9ebd-aa108eece04f)
Query 3 enables managers to see which menu items are the most popular based on the total quantity ordered. This helps with decisions such as inventory planning, promotional focus, and menu adjustments. By identifying top-selling items, managers can ensure that sufficient inventory is maintained, streamline the supply chain for these high-demand products, and potentially create promotions or bundles around them. Sorting the results in descending order highlights the best-selling items at the top, allowing managers to prioritize attention on the most impactful menu offerings.

# Database Information
Name of the database: al_Group_47114_G9

# ChatGPT Use

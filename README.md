# Team 9 Mist 4610 Group Project 1

# Team Name
Group 9

# Problem Description
Our team is designing a datamodel for "fake" local coffee shop named "Athens Cafe" where we strive to improve order processing, inventory tracking, employee management, and customer retention. 
As we all know, a coffee shop offers a diverse menu that includes a variety of coffee beverages -- ranging from classic coffee to special lattes and cold brews -- as well as coffee beans, freshly basked pastries, and branded merchandise such as mugs and tote bags.
Customers have the flexibility to place orders in-store, where they can interact with baristas and enjoy a welcoming atmosphere.
As an incentive, the coffee shop offers discounts on select items to encourage customers to return to repeat business.
The ordering process involves customers selecting their desired products, after which baristas efficiently prepare and serve the beverages while ensuring quality and efficiency.
In other words, customers order these products and are fulfilled by employees through the ordering process.
To further improve customer satisfaction, customers have the oppurtunity to provide feedback based on their experiences with us that day. Feedback is important because it helps us maintain high standards and helps us refine operations.
This datamodel will support inventory tracking by monitoring stock levels of cofee, coffee beans, and other ingredients; This ensures timely restocking and minimizing waste.
Employee management is another crucial aspect, with the system maintaining schedules, tracking hours worked, abd monitoring performance metrics to streamline workflow and optimize labor efficiency.
Ultimately, by implementing this database, "Athens Cafe" aims to enhance its ability to meet customer demands, maintain high product quality, and create a data-driven approach to running daily operations.

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
Query 1 (Simple):
Query 1 retrieves a list of all employees, displaying their EmployeeID, Name, and Role. It directly pulls the necessary information from the Employees table without any joins or filters.

<img width="450" alt="image" src="https://github.com/user-attachments/assets/73e31f53-99e8-4c1e-a7b4-6a5452c1de1d" />

This query is useful for managers and HR teams who need a quick overview of all employees within the organization, along with their roles. It can serve as a foundation for more detailed employee reports, such as identifying specific roles within departments, tracking employee performance, or even managing schedules.

Query 2 (Simple):
Query 2 retrieves the Rating and Comments from the CustomerFeedback table where the Rating is less than or equal to 3.

<img width="450" alt="image" src="https://github.com/user-attachments/assets/b7db1031-89ea-42c1-bc18-5cc3524b697a" />

This query helps managers quickly identify negative or critical customer feedback. By filtering for ratings of 3 or lower, it allows managers to focus on areas that may need attention, such as customer service or product quality. Reviewing this feedback can lead to actionable insights, allowing businesses to address customer concerns, improve their offerings, and enhance overall customer satisfaction. 

Query 3 (Simple):
Query 3 retrieves the Name, Email, and the number of customer visits (CustomerVisits) for each customer from the Customers table. 

<img width="450" alt="image" src="https://github.com/user-attachments/assets/db91e030-f89a-462f-a5f7-cd7a9aa3391f" />

This query helps businesses track the number of visits for each customer. By grouping the data by customer Name and Email, it allows the business to gain insights into customer engagement. With this information, managers can identify frequent visitors. By knowing the visit count for each customer, businesses can assess customer retention and identify potential areas for improvement in customer experience.

Query 5 (Complex):
Query 5 lists the quantity of each inventory item along with the name of the supplier that provides the item where the quantity in stock is below 100 units. The results are ordered in ascending order based on quantity, showing the items with the lowest stock first.

<img src="https://github.com/user-attachments/assets/649a7dd3-fa04-49dd-8814-a9e663ee0a35" width="450" />

Query 5 allows managers to quickly identify which inventory items are running low and which suppliers provide these items. By focusing on items with quantities below 100, managers can prioritize reordering essential ingredients, beverages, or supplies before they run out. Listing the results in ascending order based on quantity makes it easier to spot the most critically low items first, allowing for timely restocking and smooth coffee shop operations. 

Query 6 (Complex):
Query 6 lists each menu item along with the total quantity of that item ordered across all orders. It joins the MenuItems and OrderDetails tables to calculate the total quantity ordered for each item, groups the results by item, and orders them in descending order based on the total quantity ordered.

<img src="https://github.com/user-attachments/assets/e6b22d11-dd3b-407a-9ebd-aa108eece04f" width="450" />

Query 6 enables managers to see which menu items are the most popular based on the total quantity ordered. This helps with decisions such as inventory planning, promotional focus, and menu adjustments. By identifying top-selling items, managers can ensure that sufficient inventory is maintained, streamline the supply chain for these high-demand products, and potentially create promotions or bundles around them. Sorting the results in descending order highlights the best-selling items at the top, allowing managers to prioritize attention on the most impactful menu offerings.

Query 7 (Complex):
Query 7 retrieves the Name, Price, and the count of how many times each menu item has been ordered (TimesOrdered) from the MenuItems and OrderDetails tables. The results are grouped by the menu item name and price, and ordered in descending order based on the number of times each item has been ordered.

<img width="450" alt="image" src="https://github.com/user-attachments/assets/b099460f-609c-4e1a-8231-ba7c72c031ff" />

This query enables businesses to identify their top-selling menu items based on how frequently they are ordered. By joining the MenuItems and OrderDetails tables, it counts the number of times each menu item appears in customer orders. Sorting the results in descending order highlights the most popular items at the top, allowing managers to focus on high-demand products.

# Database Information
Name of the database: al_Group_47114_G9

# ChatGPT Use
In order to make sure we are being as clear as possible with where we used AI while working on this project, we are incorporating this section to lay that out. 

We began our project by asking ChatGPT,“I am the owner of a local coffee shop in Athens needing to build a relational database. I have hired some students from the MIST 4610 class at the University of Georgia to create the database for me. They need to know more about my organization to identify which entities, attributes, and relationships are important for me. Start by describing yourself as a real client . Make sure there is enough to build 10 queries (6 complex and 4 simple)”. 

This question was able to help us guide our decisions in what entities we were going to use and the attributes included in them. We used many of its ideas, but edited the response to fit what we were looking for. 

We also used ChatGPT in confirming how to describe the relationships of our data model in terms of identifying relationships and what type they were. 

Lastly, we used ChatGPT to help think of what type of queries we should use in our model; like the ideas and then we used MySQLWorkbench to create the code. 

## AdventureWorks project
### Sales of fictive bike and bike accessory manufacturing company 
The analysis can be the base of better understanding of the company operation and performance. Due to following the month over month values (Revenue, Orders, Returns) quick reactions, decisions and interventions can be made if necessary. The investigation also can be the starting point of increasing volume and market share. Analyzing previous period trends can help to draw conclusions for the future as well. Tracking most retruned products have to be developed areas can be detected.
![Riport 1](https://github.com/user-attachments/assets/a7516a3d-7cb3-4c6b-af40-f3324fd346b0)
![Riport 2](https://github.com/user-attachments/assets/ebea22e3-e29a-4fb1-b950-d2aad23e6063)
![Riport 3](https://github.com/user-attachments/assets/3b38abf4-c535-44ac-8b05-7958be95d775)
![Riport 4](https://github.com/user-attachments/assets/c065fb3c-35cf-4983-b640-284144f8d74d)
### Goal
-	Following monthly data comparing to previous month (Orders, Profit, Returns)
-	Looking for trends by temporal distribution of revenue
-	Definig transactions by product cathegories, top products and most ordered/returned product types
-	Investigating spatial distribution of transactions
-	Following monthly indicators (Orders, Revenue, Profit vs. targets) and overall performance (Orders, Revenue, Profit, Returns) of individual products
-	Scenario analysis - how unit price change of avereage product cost affects profit
-	Specify number of customers and Revenue pere customers at all and during the investigation period
-	Defining top customers, and their orders by different pont of views (income level, occupation)
### Outcome
-	Revenue shows increasing tendency in the investigation period (January of 2020 – January of 2022) and reach $24.9M in total
-	Most orders belong to Accessories product category (~17K) followed by Bikes (~13.9K) and Clothes (~7.0K)
-	Top 10 products are from Accessories and Clothes
-	Most ordered product type: Tires and Tubes
-	Most returned product type: Shorts
-	Regarding spatial distribution of transactions: United States (8.700) leads, followed by Australia (6.060) and Canada (3.024)
-	Monthly indicators and overall performance show wide range of values according to the exact product type
-	There are ~17,4K customers at all with $1.431 average revenue. Number of customers shows increase during the investigation period, but average revenue shows decrease
-	Top customer spent almost $12.4K
-	Investigation of orders by occupation shows a more or less balanced picture: Professional (7.9K), Skilled manual (6.0K), Management (4.4K)
-	Orders by income level analysis show a bit different: Average (11.6K) and Low (10.3K) income level are almost the same followed by High income level (2.8K)
### Methods and steps
-	Loading row data as multiple CSV files into Power BI Desktop
-	Checking coloumn quality, coloumn distribution, coloumn profile and data types regarding the whole data set in Power Query editor
-	Transforming data in Power Query editor in order to prepare analysis
-	Creating data model in Model view
o	Connecting data/fact table (Sales, Returns) to dimension/lookup tables (Territory, Customer, Calendar, Product, Product categories, Product subcategories) based on common ID’s and dates
o	Organizing dimension tables above fact tables in order to vizualize filters flow from up to down
o	Setting one-to-many cardinality and one-way filter dierctions
o	Hiding all foreign keys from Report view prevent to use them for filtering
![Model](https://github.com/user-attachments/assets/df3b680b-950c-4e5f-9ab8-cd549e580996)
-	Creating separate table for measures + create DAX calculations in order to use them anywhere in the report, referenced by other DAX measures and provide more complex calculations. Some of the measures:
![Total Cost](https://github.com/user-attachments/assets/85fdb6f5-6af9-458e-a623-cfb7d6db4a8c)
![Previous Month Revenue](https://github.com/user-attachments/assets/e5f1c7c5-aca8-4205-8779-5e2caaf5ebfb)
![10-day rolling revenue](https://github.com/user-attachments/assets/62aaa5e3-9e78-456b-b08c-984d5ae53aa1)
![90-day rolling profit](https://github.com/user-attachments/assets/88751816-24ff-4ff2-ab5d-78042917a024)
![YTD Revenue](https://github.com/user-attachments/assets/2eb531d0-c526-410a-a2e9-cbd10b729659)
![High Ticket Orders](https://github.com/user-attachments/assets/5333ae30-8ec3-4708-b5e1-3e96da9919e4)
-	Beyond common visualization methods some practical solution was applied too.
-	The Product detail page was set as Drilltrough page type. By choosing Drilltrough option on a product anywhere in the report Power BI automatically navigates user to the product detail page and display all calculations about the chosen product.
-	Regarding individual products Orders, Revenue, Profit, Returns and Returns % measures were used as field parameters to create the Metric Selection table, which was the input of a line chart. In this way users easily can change between measures above on the same chart, keeping the dashboard clear without overcrowding. Same solution regarding Total Customers and Revenue per Customers measures on Customer detail page.
-	Decomposition tree ensures parallelly a global picture and a detailed insight into total orders of product categories, subcategories and individual products.
-	Scenario analysis also can be applied due to possibility to change the unit price of indivudal products thereby checking impact on profit.
-	Unique category tooltip, pop-up slicers and fix panel with buttons (change between pages + clear all filters) were created too in order to increase user experience.


# Pizza Sales Report Dashboard


## Problem Statement

This report analyzes pizza sales data from January to December 2015, generating $817.86K in total revenue from 21,350 orders and 49,574 pizzas sold. 

It highlights key trends such as peak sales on Friday and Saturday evenings, large pizzas dominating with 45.89% of sales, and the Thai Chicken Pizza leading in revenue at $43K.

The findings aim to guide strategic decisions for enhancing performance and customer satisfaction.


### Steps followed 

- Step 1 : Prepare a CSV file for the dataset and create tables in the SQL.
- Step 2 : Import the CSV file to SQL.
- Step 3 : Perform some Data-Modeling in SQL through MYSQL and then import the dataset from the SQL Server into Power BI by establishing a direct connection of servers.
- Step 4 : Open the power query editor. In the view tab under the Data preview section, check the "column distribution," "column quality," and "column profile" options.
- Step 5 :  It was observed that in none of the columns errors & empty values were present 
- Step 6 : In the report view, under the view tab, theme was selected.. 
- Step 7 : Visual filters (Slicers) were added for three fields named "Pizza Size", "Order Date" & "Pizza Category".
- Step 9 : Four card new visuals were added to the canvas, representing Total Revenue, Total Orders, Total Pizza Sold, Average Order value & Average Pizza Per Order. 
           Using visual level filter from the filters pane, basic filtering was used & null values were unselected for consideration into average calculation.
           
           Although, by default, while calculating average, blank values are ignored.
 
- Step 10 : Calculated column was created to extract order day from calender.

for creating new column following DAX expression was written;
       
        order day = UPPER(LEFT(pizza_sales[Day Name],3))
        
Snap of new calculated column,

![Image](https://github.com/user-attachments/assets/d8789399-0465-4ba2-aad4-99a854a76492)


- Step 11 : Another calculated column was created to extract order month from calender.

for creating new column following DAX expression was written;

        order month = UPPER(LEFT(pizza_sales[Month Name],3))

Snap of new calculated column,

![Image](https://github.com/user-attachments/assets/12eb8394-8546-497c-97b8-0524703b98db)
        
- Step 12: New measure was created to find total revenue.

Following DAX expression was written for the same,
        
        Total Revenue = SUM(pizza_sales[total_price])       
A card visual was used to represent total revenue.

![Image](https://github.com/user-attachments/assets/e069e411-3b4a-40b4-85d7-50520bd58d5b)
        
 - Step 13 : New measure was created to find  total orders,
 
 Following DAX expression was written to find total order placed,
 
        Total Orders = DISTINCTCOUNT(pizza_sales[order_id])
 
 A card visual was used to represent this value.
 
 Snap of total orders placed by customers
 
![Image](https://github.com/user-attachments/assets/50d82d36-6f1d-4f03-984e-19436d3561a8)
 
 - Step 14 : New measure was created to calculate total pizza sold in whole year.
 
 Following DAX expression was written to find pizza sold
 
         Total Pizza Sold = SUM(pizza_sales[quantity])
    
 A card visual was used to represent this total pizza sold.
 
  Snap of total pizza sold 
 
 
![Image](https://github.com/user-attachments/assets/f4ea2d7e-cbe5-43c1-bc83-3e0a8ae90a4d)
 
 - Step 15 : New measure was created to calculate average order value in whole year.

  Following DAX expression was written to find this,
 
         Avg Order Value = [Total Revenue]/[Total Orders]

A card visual was used to represent average order value.
 
  Snap of this measure

  ![Image](https://github.com/user-attachments/assets/96eddfa9-31ee-40c1-8930-d5497a02b16e) 

   - Step 16 : New measure was created to calculate average pizza per order.

   Following DAX expression was written to find this,
 
        Avg Pizzas per Order = [Total Pizza Sold]/[Total Orders]

A card visual was used to represent average pizza per order.
 
  Snap of this measure

  ![Image](https://github.com/user-attachments/assets/2516f7dc-0ca0-4168-a1ff-cf61d6d43b01)
 
 


# Snapshot of Dashboard (Power BI Service)

![Image](https://github.com/user-attachments/assets/78ad00e2-bde2-4c27-b389-8413215c9107)


 
 # Report Snapshot (Power BI DESKTOP)

 
![Image](https://github.com/user-attachments/assets/0f1522c3-241b-47b4-8033-54a0df611bc8)


# Insights

A double page report was created on Power BI Desktop

Following inferences can be drawn from the dashboard;

### [1] Total Number of Orders = 21350

   Total revenue was $817.86K.

   Total Pizza sold 49,570.

   The average order value was $38.31.

   2.32 pizzas sold per order.



 ### [2] Some other insights
 
 ### Pizza Category
 
 1.1) Classic pizzas contributed the most sales 26.91% (14,888 units).
 
 1.2) 25.46 % revenue produced by Supreme pizzas (11,987 units).
 
 1.3) 23.96 % revenue produced by Chicken pizzas (11,050 units).

 1.4) 23.68 % revenue produced by Veggie pizzas (11,649 units).


 
         thus, maximum Classic Pizzas are at top in both sales and units sold category.
 
 ### Pizza Size
 
 2.1) 45.89 % revenue produced by Larged sized pizzas (18,956 units).
 
 2.2) 30.49 % revenue produced by Medium sized pizzas (15,635 units).
 
 2.3) 21.77 % revenue produced by Regular sized pizzas (14,403 units).

 2.4) 1.72% revenue produced by X-Large sized pizzas (552 units).

 2.5) 0.12% revenue produced by XX-Large sized pizzas(28 units).
 
         thus, Larged Sized Pizzas top the chart.         
### Pizza Name

3.1) The Thai Chicken Pizza generated the highest revenue ($43K), while the Classic Deluxe Pizza had the most orders (2,329).

3.2) The Brie Carre Pizza had the lowest revenue ($12K) and the fewest orders (480).\



### Other
Friday and Saturday evenings had the highest sales, with July and January being the peak months.

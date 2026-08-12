```markdown
# 🍕 Pizza Sales Report Dashboard

## 🧭 Problem Statement

This report analyzes pizza sales data from January to December 2015, covering $817.86K in total revenue across 21,350 orders and 49,574 pizzas sold. It surfaces key trends like peak sales on Friday and Saturday evenings, large pizzas leading at 45.89% of sales, and the Thai Chicken Pizza topping revenue at $43K. The goal is to guide decisions that improve performance and customer satisfaction.

## 🛠️ Process

- Prepared and imported the dataset into MySQL, then connected it directly to Power BI
- Checked column distribution, quality, and profile in Power Query, confirmed no errors or empty values
- Applied a report theme and added slicers for Pizza Size, Order Date, and Pizza Category
- Built KPI cards for Total Revenue, Total Orders, Total Pizza Sold, Avg Order Value, and Avg Pizzas per Order
- Created calculated columns to extract order day and order month from the calendar
- Built DAX measures to drive each KPI card

**Key DAX measures**
```
Order Day = UPPER(LEFT(pizza_sales[Day Name],3))
Order Month = UPPER(LEFT(pizza_sales[Month Name],3))
Total Revenue = SUM(pizza_sales[total_price])
Total Orders = DISTINCTCOUNT(pizza_sales[order_id])
Total Pizza Sold = SUM(pizza_sales[quantity])
Avg Order Value = [Total Revenue]/[Total Orders]
Avg Pizzas per Order = [Total Pizza Sold]/[Total Orders]


![Image](https://github.com/user-attachments/assets/d8789399-0465-4ba2-aad4-99a854a76492)
![Image](https://github.com/user-attachments/assets/12eb8394-8546-497c-97b8-0524703b98db)
![Image](https://github.com/user-attachments/assets/e069e411-3b4a-40b4-85d7-50520bd58d5b)
![Image](https://github.com/user-attachments/assets/50d82d36-6f1d-4f03-984e-19436d3561a8)
![Image](https://github.com/user-attachments/assets/f4ea2d7e-cbe5-43c1-bc83-3e0a8ae90a4d)
![Image](https://github.com/user-attachments/assets/96eddfa9-31ee-40c1-8930-d5497a02b16e)
![Image](https://github.com/user-attachments/assets/2516f7dc-0ca0-4168-a1ff-cf61d6d43b01)

## 📷 Dashboard Snapshots

**Power BI Service**
![Image](https://github.com/user-attachments/assets/78ad00e2-bde2-4c27-b389-8413215c9107)

**Power BI Desktop**
![Image](https://github.com/user-attachments/assets/0f1522c3-241b-47b4-8033-54a0df611bc8)

## 💡 Insights

**Overall**
- 21,350 total orders and 49,570 pizzas sold
- $817.86K total revenue, $38.31 average order value
- 2.32 pizzas sold per order on average

**By Category**
- Classic: 26.91% of sales, 14,888 units, the top performer overall
- Supreme: 25.46% of sales, 11,987 units
- Chicken: 23.96% of sales, 11,050 units
- Veggie: 23.68% of sales, 11,649 units

**By Size**
- Large: 45.89% of revenue, 18,956 units, the clear leader
- Medium: 30.49% of revenue, 15,635 units
- Regular: 21.77% of revenue, 14,403 units
- X-Large: 1.72% of revenue, 552 units
- XX-Large: 0.12% of revenue, 28 units

**By Product**
- Thai Chicken Pizza generated the most revenue at $43K
- Classic Deluxe Pizza had the most orders at 2,329
- Brie Carre Pizza had the lowest revenue at $12K and fewest orders at 480

**Timing**
- Friday and Saturday evenings were the highest sales windows
- July and January were the peak months

## 🧠 Things I Learned

- Connecting Power BI directly to a MySQL server gave me a much better sense of how data modeling decisions upstream affect what is possible downstream in the report
- Writing DAX measures like DISTINCTCOUNT and simple division measures taught me the difference between a calculated column and a measure, and when each one actually belongs
- Checking column quality and distribution in Power Query before building anything saved me from chasing phantom errors later in the report
- Breaking revenue down by category, size, and product at the same time showed me how one dimension can hide a trend that another one reveals clearly
- Small naming conventions, like uppercasing day and month abbreviations, make slicers and axis labels far more readable for anyone viewing the report

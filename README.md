## Sales-Insights-Data-Analysis-Simple-Project-for-Beginner-Level
This project features an interactive sales dashboard developed using SQL, Excel, and Power BI to analyze retail performance over the past four years. It enables users to filter data by year and product category, providing an in-depth view of business trends. The dashboard highlights key metrics such as total revenue by year, sales distribution and units sold by category. Overall, it offers a clear, data-driven understanding of sales patterns, helping identify high-performing categories. 

### Source Data
The dashboard is built using single which was synthetically generated using AI to simulate realistic sales transactions for analysis and visualization purposes.
- sales_data.csv – contains information about sales such as: Product ID, Order ID, Product Name, Customer ID, Customer Name, Quantity, Order Date, Unit Price, Total Price, Category.

## Tools Used:
- MS SQL 
- Excel
- Power BI
- Tableau 

## SQL QUERY

##### Total Revenue 

```sql
select sum(Total_Price) as Total_Revenue
from sales_data
```

<img width="213" height="90" alt="image" src="https://github.com/user-attachments/assets/666c12ae-932c-4885-9fd7-198528359eb2" />


##### Average Order Value

```sql
select sum(Total_Price)/ count(Distinct Order_ID) As Avg_Order_Value
from sales_data
```

<img width="213" height="90" alt="image" src="https://github.com/user-attachments/assets/9b0fe1aa-b2f4-4164-a1f7-6d030f891489" />



##### Total product sold

```sql
select sum(Quantity) As Total_Product_Sold
from sales_data
```

<img width="213" height="95" alt="image" src="https://github.com/user-attachments/assets/669dea3c-fd66-47f7-8006-f32f7e68aa9f" />


##### Total orders

```sql
select count
(Distinct Order_ID) As Total_Order
from sales_data
```

<img width="213" height="90" alt="image" src="https://github.com/user-attachments/assets/1f410e9a-2977-4533-8809-189c1576de2c" />


##### Average Product Per Order


```sql
select sum(Quantity)/ count(Distinct Order_ID) As Avg_product_per_order
from sales_data
```

<img width="217" height="90" alt="image" src="https://github.com/user-attachments/assets/3fdf6c96-8e21-4bae-9da2-168591fb8e06" />


##### Percentage of Sales by Category

```sql
select Category, SUM(Total_Price) as Total_Sales , SUM(Total_Price) * 100 / (select SUM(Total_price) from sales_data) AS Sale_percentage
from sales_data
Group by Category
```

<img width="439" height="150" alt="image" src="https://github.com/user-attachments/assets/255eb2aa-0d7a-418e-b4d2-f002eb64d18d" />



##### Product Sold by Category

```sql
select Category, SUM(Quantity) as Total_Product_Sold 
from sales_data
Group by Category
```

<img width="358" height="150" alt="image" src="https://github.com/user-attachments/assets/8351c52a-cc87-4985-bc7b-d0090ae79d55" />



##### Top 5 Products


```sql
select TOP 5 Product_Name, SUM(Quantity) as Total_Product_Sold 
from sales_data
Group by Product_Name
Order by Total_Product_Sold  DESC
```

<img width="300" height="156" alt="image" src="https://github.com/user-attachments/assets/93b4dc8f-f35f-4f0e-a443-1b7343cba36a" />



##### Top 5 Customer

```sql
select TOP 5 Customer_Name, SUM(Total_Price) as Total_Purchase_Amount
from sales_data
Group by Customer_Name
Order by Total_Purchase_Amount DESC
```

<img width="319" height="157" alt="image" src="https://github.com/user-attachments/assets/4f652181-7d5e-456c-a26a-46c29aab0401" />


## Excel Dashboard


<img width="700" height="581" alt="image" src="https://github.com/user-attachments/assets/a0b1564c-b669-4a4c-bf50-3215a997bc11" />

## Power BI Dashboard


<img width="700" height="581" alt="image" src="https://github.com/user-attachments/assets/eeea8ef5-053e-426b-b158-b07a50bee028" />


<img width="700" height="581" alt="image" src="https://github.com/user-attachments/assets/f8552143-18ef-4465-928f-063116e1a886" />



## Tableau Dashboard

<img width="700" height="581" alt="image" src="https://github.com/user-attachments/assets/d0036c69-8974-49cd-8ca0-bff307019225" />










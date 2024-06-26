# DynamicSalesInsights-PowerBI
## Overview 📊
Welcome to the Sales Insights Data Analysis Project! This project aims to provide real-time sales insights for a computer hardware business facing market challenges. The goal is to build a Power BI dashboard that delivers actionable insights using data analysis techniques.

## Project Structure 🏗️
The project is divided into the following main parts:

1. MySQL Database Setup 🛠️
2. Data Analysis Using SQL 🧩
3. Data Analysis Using Power BI 📈
4. Power BI Dashboard 🖥️
   
## MySQL Database Setup 🛠️
Follow the steps in this video tutorial to install MySQL on your local computer.
https://www.youtube.com/watch?v=WuBcTJnIuzo

### Instructions
📥 Download the db_dump.sql file from this repository.
📂 Import the db_dump.sql file into your MySQL database as per the instructions given in the tutorial video.
## Data Analysis Using SQL 🧩
Use the following SQL queries to perform the data analysis:
1. Show all customer records

    `SELECT * FROM customers;`

2. Show total number of customers

    `SELECT count(*) FROM customers;`

3. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

4. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

5. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

6. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

7. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
8. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

9. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`

## Data Analysis Using Power BI 📈
Follow these steps to analyze the data and create a dashboard in Power BI:

1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`

2. Create visualizations and build your dashboard based on the analysis requirements.


## Power BI Dashboard 🖥️
The Power BI dashboard provides a comprehensive overview of the sales data, including key metrics and insights to aid decision-making.

## Structure 📂
db_dump.sql - The SQL dump file for setting up the database.

PowerBI_Dashboard.pbix - The Power BI dashboard file.

README.md - This README file.

## Getting Started 🚀
To get started with this project:

🖥️ Clone this repository to your local machine.

📂 Set up the MySQL database using the provided db_dump.sql file.

📈 Open the Power BI dashboard file (Sales Insights of AtliQ Hardware.pbix) to view the visualizations and insights.

## Contributing 🤝
Contributions are welcome! Please fork the repository and submit a pull request with your changes.



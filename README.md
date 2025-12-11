# retail-Sales-Analysis-Using-SQL-PLSQL-Queries-Triggers-Procedures
complete DBMS project analyzing retail sales data with queries, aggregate functions, triggers, procedures, cursors, and PL/SQL blocks. Includes dataset, scripts

Project Title: Retail Sales Analysis
Level: Beginner
Database: p1_retail_db

This project is designed to demonstrate SQL skills and techniques typically used by data analysts to explore, clean, and analyze retail sales data. The project involves setting up a retail sales database, performing exploratory data analysis (EDA), and answering specific business questions through SQL queries. This project is ideal for those who are starting their journey in data analysis and want to build a solid foundation in SQL.

Objectives
Set up a retail sales database: Create and populate a retail sales database with the provided sales data.
Data Cleaning: Identify and remove any records with missing or null values.
Exploratory Data Analysis (EDA): Perform basic exploratory data analysis to understand the dataset.
Business Analysis: Use SQL to answer specific business questions and derive insights from the sales data.

TABLE CREATION
CREATE TABLE sales_retail
            ( transaction_id number(10) PRIMARY KEY,	
                sale_date DATE,	 
                sale_time timestamp,	
                customer_id number(10),
                gender	VARCHAR2(15),
                age	number(3),
                category VARCHAR2(15),	
                quantity number(10),
                price_per_unit number(10),	
                cogs number(10),
                total_sales number(10)
            );
INSERT  INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
values (522, DATE '2022-07-09', TO_DATE('11:00:00','HH24:MI:SS'), 52, 'Male', 46, 'Beauty', 3, 500, 145, 1500);
INSERT  INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
values (559, DATE '2022-12-12', TO_DATE('10:48:00','HH24:MI:SS'), 5, 'Female', 40, 'Clothing', 4, 300, 84, 1200);
INSERT  INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
values (1180, DATE '2022-01-06', TO_DATE('08:53:00','HH24:MI:SS'), 85, 'Male', 41, 'Clothing', 3, 300, 129, 900);
iNSERT  INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
values(1522, DATE '2022-11-14', TO_DATE('08:35:00','HH24:MI:SS'), 48, 'Male', 46, 'Beauty', 3, 500, 235, 1500);
INSERT  INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (547, DATE '2022-08-20', TO_DATE('07:40:00','HH24:MI:SS'), 49, 'Female', 40, 'Clothing', 4, 300, 144, 1200);
INSERT  INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (1630, DATE '2022-10-31', TO_DATE('09:38:00','HH24:MI:SS'), 144, 'Female', 64, 'Clothing', 3, 50, 23, 150);
INSERT  INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (1303, DATE '2022-04-22', TO_DATE('11:09:00','HH24:MI:SS'), 54, 'Male', 19, 'Electronics', 3, 30, 14.7, 90);
INSERT  INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (1421, DATE '2022-04-08', TO_DATE('08:43:00','HH24:MI:SS'), 66, 'Female', 37, 'Clothing', 3, 500, 235, 1500);
INSERT INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (2979, DATE '2022-06-18', TO_DATE('10:18:00','HH24:MI:SS'), 6, 'Female', 19, 'Beauty', 1, 25, 10.5, 25);
INSERT  INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (1163, DATE '2022-05-04', TO_DATE('10:52:00','HH24:MI:SS'), 120, 'Female', 64, 'Clothing', 3, 50, 27, 150);
INSERT  INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (303, DATE '2022-03-19', TO_DATE('08:59:00','HH24:MI:SS'), 58, 'Male', 19, 'Electronics', 3, 30, 15, 90);
INSERT  INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (421, DATE '2022-04-08', TO_DATE('08:43:00','HH24:MI:SS'), 66, 'Female', 37, 'Clothing', 3, 500, 235, 1500);
INSERT INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (979, DATE '2022-05-18', TO_DATE('10:18:00','HH24:MI:SS'), 6, 'Female', 19, 'Beauty', 1, 25, 10.5, 25);
INSERT INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (1063, DATE '2022-05-04', TO_DATE('10:52:00','HH24:MI:SS'), 120, 'Female', 64, 'Clothing', 3, 50, 27, 150);
INSERT INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (1313, DATE '2022-03-19', TO_DATE('08:59:00','HH24:MI:SS'), 58, 'Male', 19, 'Electronics', 3, 30, 15, 90);
INSERT INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (1401, DATE '2022-01-17', TO_DATE('07:07:00','HH24:MI:SS'), 59, 'Female', 37, 'Clothing', 3, 500, 185, 1500);
INSERT INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (1979, DATE '2022-08-17', TO_DATE('11:34:00','HH24:MI:SS'), 102, 'Female', 19, 'Beauty', 1, 25, 7.75, 25);
INSERT INTO sales (transaction_id, sale_date, sale_time, customer_id, gender, age, category, quantity, price_per_unit, cogs, total_sales)
VALUES (610, DATE '2022-12-18', TO_DATE('06:56:00','HH24:MI:SS'), 137, 'Female', 26, 'Beauty', 2, 300, 93, 600);
SELECT * FROM SALES;
---count total transaction 
select count from sales_retail;

--data cleaning
select * from sales_retail where transaction_id is null;
or
sale_date is null
0r
sale_time is null
or
gender is null
or
category is null
or
uantity IS NULL
OR
cogs IS NULL
OR
total_sales IS NULL;

--total revenue sum

SELECT SUM (total_sale)
 FROM retail_sales;

---highest sale amount

select max(TOTAL_SALE) as highest
 from retail_sales;

----daily sales by date

select sale_date,sum(TOTAL_SALE) as daily_sales 
from retail_sales 
group by sale_date
 order by sale_date;

--category wise total quantity

select category,sum(TOTAL_SALE) as total_quantity 
from retail_sales
 group by category
  order by total_quantity desc;

--gender wise total customers

select gender, count(*) as total_customers 
from retail_sales 
group by gender;

--min and max age of customers

select min(age) as youngest, max(age) as oldest
 from retail_sales;

----which day has the highest sales

select sale_date,sum(TOTAL_SALE) from retail_sales 
group by sale_date 
order by sale_date desc;

---which category has the highest highest revenue

select category,sum(TOTAL_SALE) as revenue from retail_sales
 group by category order by 
 revenue desc;

--calculate total sales=category * price per unit for each transaction

select transaction_id,quantity,price_per_unit,quantity * price_per_unit as calculated_total_sales
 from retail_sales;

--total revenue generated

SELECT sum(TOTAL_SALE) total_revenue
 from retail_sales;

--find sales by hour of the day 

SELECT 
    EXTRACT(HOUR FROM sale_time) AS hour_of_day,
    COUNT(*) AS total_transactions
FROM retail_sales
GROUP BY EXTRACT(HOUR FROM sale_time)
ORDER BY hour_of_day;

---profit profit = total sale - cogs

select category, sum(TOTAL_SALE-cogs) as profit from retail_sales group by category order by profit desc;

--find customer by age group

SELECT 
    CASE 
        WHEN age BETWEEN 18 AND 25 THEN '18-25'
        WHEN age BETWEEN 26 AND 35 THEN '26-35'
        WHEN age BETWEEN 36 AND 50 THEN '36-50'
        ELSE '50+'
    END AS age_group,
    SUM(TOTAL_SALE) AS group_sales
FROM retail_sales
GROUP BY 
    CASE 
        WHEN age BETWEEN 18 AND 25 THEN '18-25'
        WHEN age BETWEEN 26 AND 35 THEN '26-35'
        WHEN age BETWEEN 36 AND 50 THEN '36-50'
        ELSE '50+'
    END;

peak shopping day (most transaction)

SELECT 
    sale_date,
    COUNT(*) AS transaction_count
FROM retail_sales
GROUP BY sale_date
ORDER BY transaction_count DESC;

--CATEGORY WITH HIGHEST AVG QUANTITY

SELECT 
    category,
    AVG(quantity) AS avg_quantity
FROM retail_sales
GROUP BY category
ORDER BY avg_quantity DESC;
--add discount to the retail_sales

 alter table retail_sales add discount_amount number(10,2);

--drop column discount amount
alter table retail_sales drop column discount_amount;

--Write a PL/SQL block to print all sales records where total_sale > 1000

DECLARE
   -- Cursor to fetch records with total_sale > 1000
   CURSOR c_sales IS
      SELECT transaction_id, sale_date, sale_time, customer_id, gender, age, category,
             quantity, price_per_unit, cogs, total_sale
      FROM retail_sales
      WHERE total_sale > 1000;

   -- Variables to hold each column value
   v_transaction_id retail_sales.transaction_id%TYPE;
   v_sale_date       retail_sales.sale_date%TYPE;
   v_sale_time       retail_sales.sale_time%TYPE;
   v_customer_id     retail_sales.customer_id%TYPE;
   v_gender          retail_sales.gender%TYPE;
   v_age             retail_sales.age%TYPE;
   v_category        retail_sales.category%TYPE;
   v_quantity         retail_sales.quantity%TYPE;
   v_price_per_unit  retail_sales.price_per_unit%TYPE;
   v_cogs            retail_sales.cogs%TYPE;
   v_total_sale      retail_sales.total_sale%TYPE;
BEGIN
   OPEN c_sales;
   LOOP
      FETCH c_sales INTO v_transaction_id, v_sale_date, v_sale_time, v_customer_id,
                        v_gender, v_age, v_category, v_quantity, v_price_per_unit,
                        v_cogs, v_total_sale;
      EXIT WHEN c_sales%NOTFOUND;

      -- Print each record
      DBMS_OUTPUT.PUT_LINE(
         'Txn_ID: ' || v_transaction_id ||
         ', Date: ' || TO_CHAR(v_sale_date,'YYYY-MM-DD') ||
         ', Time: ' || v_sale_time ||
         ', Cust_ID: ' || v_customer_id ||
         ', Gender: ' || v_gender ||
         ', Age: ' || NVL(TO_CHAR(v_age),'NULL') ||
         ', Category: ' || v_category ||
         ', Quantity: ' || v_quantity ||
         ', Price: ' || v_price_per_unit ||
         ', COGS: ' || v_cogs ||
         ', Total Sale: ' || v_total_sale
      );
   END LOOP;
   CLOSE c_sales;
END;
/
DESC retail_sales;
BEGIN
   FOR rec IN (
      SELECT transaction_id, sale_date, sale_time, customer_id, gender, age, category,
             quantity, price_per_unit, cogs, total_sale
      FROM retail_sales
      WHERE total_sale > 1000
   )
   LOOP
      DBMS_OUTPUT.PUT_LINE(
         'Txn_ID: ' || rec.transaction_id ||
         ', Date: ' || TO_CHAR(rec.sale_date,'YYYY-MM-DD') ||
         ', Cust_ID: ' || rec.customer_id ||
         ', Category: ' || rec.category ||
         ', Total Sale: ' || rec.total_sale
      );
   END LOOP;
END;
/
SET SERVEROUTPUT ON;

SELECT * FROM retail_sales WHERE total_sale > 1000;

-- Create a procedure update_price that increases price_per_unit by 10% for a given category.
create or replace procedure update_price(p_category in varchar2)
IS
BEGIN
    update retail_sales
    set price_per_unit = price_per_unit * 1.10 where category = p_category;
    commit;
    DBMS_OUTPUT.PUT_LINE('Price updated successfully for category: ' || p_category);
EXCEPTION
   WHEN OTHERS THEN
      DBMS_OUTPUT.PUT_LINE('Error: ' || SQLERRM);
END;
/
SELECT category, price_per_unit
FROM retail_sales
WHERE category = 'Beauty';

BEGIN
   update_price('Beauty');   -- or any category name
END;
/

select category,price_per_unit 
from retail_sales
where category = 'clothing';

BEGIN
    update_price('clothing');
end;
/

--Write a function get_daily_sales(p_date DATE) that returns the total sales for that date.
CREATE OR REPLACE FUNCTION get_daily_sales(p_date IN DATE)
RETURN NUMBER
IS
   v_total NUMBER := 0;
BEGIN
   SELECT NVL(SUM(total_sale), 0)
   INTO v_total
   FROM retail_sales
   WHERE sale_date = p_date;

   RETURN v_total;

EXCEPTION
   WHEN OTHERS THEN
      DBMS_OUTPUT.PUT_LINE('Error: ' || SQLERRM);
      RETURN 0;
END;
/

DESC retail_sales;

SELECT get_daily_sales(DATE '2022-11-05') AS total_sales
FROM retail_sales;
SELECT get_daily_sales(DATE '2022-07-09') FROM retail_sales;

--Write a trigger that prevents insertion of records where total_sale is less than 50.
create or replace trigger trg_check_total_sale 
before insert  on retail_sales
for each rowS
BEGIN
    if: new.total_sale < 50 THEN
    RAISE_APPLICATION_ERROR(-20001, 'Total sale must be at least 50. Insertion not allowed.');
   END IF;
END;
 /


  SELECT total_sale
FROM retail_sales 
WHERE total_sale < 50;
  
 -- Write a cursor to fetch all sales records for the category 'Electronics'. --


DECLARE
    cursor electronics_cursor 
    IS
    SELECT * 
        FROM retail_sales
        WHERE category = 'Electronics';
  sale_record retail_sales%ROWTYPE;  
BEGIN
    OPEN electronics_cursor;
 LOOP
        -- Step 4: Fetch each row into the record
        FETCH electronics_cursor INTO sale_record;
        
        -- Exit the loop when no more rows
        EXIT WHEN electronics_cursor%NOTFOUND;
        
        -- Step 5: Do something with the fetched row
        DBMS_OUTPUT.PUT_LINE('Transaction ID: ' || sale_record.transaction_id ||
                             ', Customer ID: ' || sale_record.customer_id ||
                             ', Price: ' || sale_record.price_per_unit ||
                             ', Quantity: ' || sale_record.quantity);
    END LOOP;
    
    -- Step 6: Close the cursor
    CLOSE electronics_cursor;
END;
/ 
 
--write a cursor to display customer IDs and their total purchases.

SET SERVEROUTPUT ON;

DECLARE
    -- Cursor to fetch total purchases per customer
    CURSOR customer_total_cursor IS
        SELECT customer_id, SUM(total_sale) AS total_purchase
        FROM retail_sales
        GROUP BY customer_id;
    
    customer_record customer_total_cursor%ROWTYPE;
BEGIN
    OPEN customer_total_cursor;
    
    LOOP
        FETCH customer_total_cursor INTO customer_record;
        EXIT WHEN customer_total_cursor%NOTFOUND;
        
        DBMS_OUTPUT.PUT_LINE('Customer ID: ' || customer_record.customer_id ||
                             ', Total Purchase: ' || customer_record.total_purchase);
    END LOOP;
    
    CLOSE customer_total_cursor;
END;
/

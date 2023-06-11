# EXPERIMENT 08:IMPLEMENT THE KEYWORD-CASE,CROSS JOIN,FULL OUTER JOIN
## AIM:
To do operations on sql using keywords CASE,CROSS JOIN,FULL OUTER JOIN.

## ALGORITHM:
1. Create a table named Employee.
2. Insert the values inside the table.
3. Perform operations using case for a specific consition.
4. Use keyword cross join for two tables.
5. Also perform full outer join between two tables.
6. Display the values as output.
## PROGRAM:
### Case:
```
CREATE TABLE EMPLOYEE (
  empId INTEGER PRIMARY KEY,
  firstname TEXT NOT NULL,
  lastname TEXT NOT NULL,
  salary INTEGER NOT NULL
);
--insert
INSERT INTO EMPLOYEE VALUES (0001, 'Harry', 'potter',1000);
INSERT INTO EMPLOYEE VALUES (0002, 'Dave', 'John',3500);
INSERT INTO EMPLOYEE VALUES (0003, 'Ava', 'Grayson',7000);
INSERT INTO EMPLOYEE VALUES (0004, 'Eda', 'Srikar',1200);
INSERT INTO EMPLOYEE VALUES (0005, 'Robert', 'Brown',2500);
INSERT INTO EMPLOYEE VALUES (0006, 'Will', 'John',9000);

SELECT empId,firstname,lastname,salary,
CASE
WHEN salary<3000 THEN "Low"
WHEN salary>3000 AND salary<5000 THEN "Average"
ELSE "High"
END AS result
FROM EMPLOYEE;
```
### Cross Join:
```
CREATE TABLE sales_organization 
(
	sales_org_id INT PRIMARY KEY,
	sales_org VARCHAR (255)
);
CREATE TABLE sales_channel 
(
	channel_id INT PRIMARY KEY,
	channel_name VARCHAR (255)
);
INSERT INTO sales_organization (sales_org_id, sales_org)
VALUES
(1, 'Domestic'),
(2, 'Export');
INSERT INTO sales_channel (channel_id, channel_name)
VALUES
(1, 'Wholesale'),
(2, 'Retail'),
(3, 'eCommerce'),
(4, 'TV Shopping');
SELECT
sales_org,
channel_name
FROM
sales_organization
CROSS JOIN sales_channel;
```
### Full Outer Join:
```
CREATE TABLE fruits (
fruit_id INTEGER PRIMARY KEY,
fruit_name VARCHAR (255) NOT NULL,
basket_id INTEGER
);
CREATE TABLE baskets (
basket_id INTEGER PRIMARY KEY,
basket_name VARCHAR (255) NOT NULL
);
INSERT INTO baskets (basket_id, basket_name)
VALUES
(1, 'A'),
(2, 'B'),
(3, 'C');
INSERT INTO fruits (fruit_id,fruit_name,basket_id)
VALUES
(1, 'Apple', 1),
(2, 'Orange', 1),
(3, 'Banana', 2),
(4, 'Strawberry', NULL);
SELECT
basket_name,
fruit_name
FROM
fruits
FULL OUTER JOIN baskets ON baskets.basket_id = fruits.basket_id;
```
## OUTPUT:
### Case:
![image](https://github.com/Rithigasri/DBMS-EXP8/assets/93427256/a91b0dce-0325-44c2-bab6-417bd3f198e2)

### Cross join:
![image](https://github.com/Rithigasri/DBMS-EXP8/assets/93427256/ac0626b6-8152-4125-809b-f9446539078b)
### Full outer join:
![image](https://github.com/Rithigasri/DBMS-EXP8/assets/93427256/b431c943-313c-433c-b180-eb27051cf2fa)


## RESULT:
Hence, the implementation of keywords case,cross join,full outer join is executed successfully.

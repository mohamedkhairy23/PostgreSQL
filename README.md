# SQL Shell (PostgreSQL):-

## For creating a database:

- CREATE DATABASE database-name;

## For displaying a list of databases:

- \l

## To drop a database:

- DROP DATABASE database-name;

## To clear terminal:

- \! cls

## Help commands:

- \h for help with SQL commands
- \? for help with PostgreSQL commands

## Connect to a new database:

- \c[onnect] {[DBNAME|- USER|- HOST|- PORT|-]}

## For changing database password:

- \password

## Displaying database connection info:

- \conninfo

## Example for creating a table with table columns in store database:

- \c store
- press enter
- store=# CREATE TABLE IF NOT EXISTS customer(
- press enter
- store(# id SERIAL PRIMARY KEY NOT NULL,
- press enter
- store(# full_name VARCHAR(50) NOT NULL,
- press enter
- store(# email VARCHAR(60) UNIQUE NOT NULL,
- press enter
- store(# date_of_birth DATE,
- press enter
- store(# created_at TIMESTAMP);
- press enter

## Other example for creating a table with table columns in store database:

- store=# CREATE TABLE products(
- press enter
- store(# id SERIAL PRIMARY KEY,
- press enter
- store(# name VARCHAR(50) NOT NULL,
- press enter
- store(# description TEXT NOT NULL,
- press enter
- store(# price NUMERIC(10, 2) NOT NULL,
- press enter
- store(# qty INT NOT NULL,
- press enter
- store(# created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
- press enter
- store(# updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP);
- press enter

## For descriping databases:

- \d

## Describe Database Table:

- \d table_name
- \d customer

## To drop a specific table:

- DROP TABLE table-name;
- DROP TABLE customer;

## Modify Column Data Type (Modify data type of the column named created_at from TIMESTAMP TO CURRENT_TIMESTAMP):

- ALTER TABLE customer ALTER COLUMN created_at SET DEFAULT CURRENT_TIMESTAMP;

## Insert A New Record Into Table:

- INSERT INTO customer (email, full_name, date_of_birth) VALUES ('test@test.com', 'Mohamed Khairy', '2024-05-05');

## Select Columns From Table:

- SELECT \* FROM customer;

- SELECT full_name, email from customer;

## Add New Column (Example):

- ALTER TABLE customer ADD COLUMN updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP;

## Drop Default Value:

- ALTER TABLE customer ALTER COLUMN updated_at DROP DEFAULT;

## To run sql file (Example):

- \i file_path
- \i C:/Users/KHAIRY/Desktop/PostgreSQL/productsData.sql

## Delete table records with undo (Transaction):

- BEGIN;
- DELETE FROM products;
- ROLLBACK;
- COMMIT;

## Notes:

- BEFIN for starting tranaction, and COMMIT for closing transaction.
- ROLLBACK for undo transactions in progress.
- To can make ROLLBACK, It's must to be in transaction.

## Delete table records without undo (TRUNCATE):

- TRUNCATE TABLE products;

## Select Rows With Condition:

- SELECT id, name, price from products WHERE id >= 180;
- SELECT id, name, price FROM products WHERE price BETWEEN 250 and 900;
- SELECT id, name, price FROM products WHERE price = 731 OR price = 407;

## Filteration operators:

- SELECT id, name, price FROM products LIMIT 20;
- SELECT id, name, price FROM products WHERE name LIKE '%Steel%';
- SELECT id, name, price FROM products WHERE name LIKE '%Steel%' LIMIT 3;

## Duplicate A Specific Row In A Table:

- INSERT INTO products (name, description, price, qty) SELECT name, description, price, qty FROM products WHERE id = 175;
- SELECT id, name, price FROM products WHERE name LIKE 'Gorgeous Bronze Cheese';

## Find Duplicated Rows (Rows that contain the same name):

- SELECT name, COUNT(\*) FROM products GROUP BY name HAVING COUNT(\*) > 1;

## Find Duplicated Rows (Rows that contain the same name, and the same price):

- SELECT name, price, COUNT(\*) FROM products GROUP BY name, price HAVING COUNT(\*) > 1;

## Order By Clause (Sorting):

- SELECT id, name, price FROM products ORDER BY id ASC LIMIT 25;
- SELECT id, name, price FROM products ORDER BY id DESC LIMIT 25;
- SELECT id, name, price FROM products ORDER BY price DESC LIMIT 25;
- SELECT id, name, price FROM products ORDER BY price DESC;

## Notes:

- ASC (from small to large)
- DESC (from large to small)

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

store=# CREATE TABLE products(
store(# id SERIAL PRIMARY KEY,
store(# name VARCHAR(50) NOT NULL,
store(# description TEXT NOT NULL,
store(# price NUMERIC(10, 2) NOT NULL,
store(# qty INT NOT NULL,
store(# created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
store(# updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP);

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
- \i C:/Users/ELBOSTAN/Desktop/PostgreSQL/productsData.sql

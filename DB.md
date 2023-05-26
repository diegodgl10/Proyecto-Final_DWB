Creacion de DB

```
SHOW TABLES;

USE dwb_proyecto;

CREATE TABLE category (category_id INT PRIMARY KEY, category VARCHAR(100), acronym VARCHAR(50), status INT);

CREATE TABLE product (product_id INT PRIMARY KEY, gtin VARCHAR(100), product VARCHAR(100), description VARCHAR(100), price DOUBLE, stock INT, category_id INT, status INT);

CREATE TABLE region (region_id INT PRIMARY KEY, region VARCHAR(100), status INT);

CREATE TABLE customer_image (customer_image_id INT PRIMARY KEY, customer_image VARCHAR(100));

CREATE TABLE customer (customer_id INT PRIMARY KEY, name VARCHAR(100), surname VARCHAR(100), date_birth DATE, rfc VARCHAR(15), mail VARCHAR(50), address VARCHAR(100), status INT, region_id INT, customer_image_id INT, FOREIGN KEY (region_id) REFERENCES region(region_id), FOREIGN KEY (customer_image_id) REFERENCES customer_image(customer_image_id));

CREATE TABLE cart (cart_id INT PRIMARY KEY, rfc VARCHAR(15), gtin VARCHAR(100), quantity INT, status INT);

CREATE TABLE invoice (invoice_id INT PRIMARY KEY, rfc VARCHAR(15), subtotal DOUBLE, taxes DOUBLE, total DOUBLE, created_at DATE, status INT);

CREATE TABLE item (item_id INT PRIMARY KEY, invoice_id INT, gtin VARCHAR(100), quantity INT, unit_price DOUBLE, subtotal DOUBLE, taxes DOUBLE, total DOUBLE, status INT);

```
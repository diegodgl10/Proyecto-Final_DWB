# Proyecto 1

## Zamora Cruz Diego Arturo - 316249560

El proyecto fue programado y probado con

- Spring Boot: 2.7.8
- Java: 11
- Eclipse IDE: 2022-09
- Postman: 10.10.9
- MySQL 8.0.32
  * base de datos: `dwb_proyecto`
  * usuario: `root`
  * password: `123456`


- Repositorio de [/config-data-dwb](https://github.com/diegodgl10/config-data-dwb)
- Aplicacion de [Spring Boot](http://localhost:8090/applications)

### Antes de la ejecución

Crear una base de datos llamada `dwb_proyecto`

Crear la tabla

Crear la tabla `category` con columnas:
- *category_id* llave de tipo INT
- *category* de tipo VARCHAR
- *acronym* de tipo VARCHAR
- *status* de tipo INT

Crear la tabla `product` con columnas:
- *product_id* llave de tipo INT
- *gtin* de tipo VARCHAR
- *product* de tipo VARCHAR
- *description* de tipo VARCHAR
- *price* de tipo DOUBLE
- *stock* de tipo INT
- *category_id* de tipo INT
- *status* de tipo INT

Crear la tabla `region` con columnas:
- *region_id* llave de tipo INT
- *region* de tipo VARCHAR
- *status* de tipo INT

Crear la tabla `customer_image` con columnas:
- *customer_image_id* llave de tipo INT
- *customer_image* de tipo VARCHAR

Crear la tabla `customer` con columnas:
- *customer_id* llave de tipo INT
- *name* de tipo VARCHAR
- *surname* de tipo VARCHAR
- *date_birth* de tipo DATE
- *rfc* de tipo VARCHAR
- *mail* de tipo VARCHAR
- *address* de tipo VARCHAR
- *status* de tipo INT
- *region_id* de tipo INT
- *customer_image_id* de tipo INT
- *region_id* referente a `region`*(region_id)*
- *customer_image_id* referente a `customer_image`*(customer_image_id)*

Crear la tabla `cart` con columnas:
- *cart_id* llave de tipo INT
- *rfc* de tipo VARCHAR
- *gtin* de tipo VARCHAR
- *quantity* de tipo INT
- *status* de tipo INT

Crear la tabla `invoice` con columnas:
- *invoice_id* llave de tipo INT
- *rfc* de tipo VARCHAR
- *subtotal* de tipo DOUBLE
- *taxes* de tipo DOUBLE
- *total* de tipo DOUBLE
- *created_at* de tipo DATE
- *status* de tipo INT

Crear la tabla `item` con columnas:
- *item_id* llave de tipo INT
- *invoice_id* de tipo INT
- *gtin* de tipo VARCHAR
- *quantity* de tipo INT
- *unit_price* de tipo DOUBLE
- *subtotal* de tipo DOUBLE
- *taxes* de tipo DOUBLE
- *total* de tipo DOUBLE
- *status* de tipo INT


### Ejecucion del software

1. Ejecutamos el programa son el software de su preferencia (spring tool suite, NetBeans, etc.)
2. Para probar cada metodo programado, se uso Postman, por lo que se recomienda tambien usarlo.



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
# Proyecto

## Zamora Cruz Diego Arturo - 316249560

La proyecto fue programada y probada con

- Spring Boot: 2.7.8
- Java: 11
- Eclipse IDE: 2022-09
- Postman: 10.10.9
- MySQL 8.0.32
  * base de datos: `dwb_proyecto`
  * usuario: `root`
  * password: `123456`


Repositorio de [/config-data-dwb](https://github.com/diegodgl10/config-data-dwb)

Instrucciones de ejecución

### Creacion de la tabla Category

Dentro de la base de datos, creamos una tabla llamada `category` con columnas
   * *category_id* : llave de tipo int.
   * *category* : de tipo varchar(100).
   * *acronym* : de tipo varchar(50).
   * *status* : de tipo int.

| ![](phpMyAdmin_category.png)
|:----------------------:|
| Configuracion de tabla `category` en phpMyAdmin.


### Creacion de la tabla Product

Dentro de la base de datos, creamos una tabla llamada `product` con columnas
   * *product_id* : llave de tipo int.
   * *gtin* : de tipo varchar(100).
   * *product* : de tipo varchar(100).
   * *description* : de tipo varchar(100).
   * *price* : de tipo double.
   * *stock* : de tipo int.
   * *category_id* : de tipo int.
   * *status* : de tipo int.

| ![](phpMyAdmin_product.png)
|:----------------------:|
| Configuracion de tabla `product` en phpMyAdmin.


### Ejecucion del software

1. Ejecutamos el programa son el software de su preferencia (spring tool suite, NetBeans, etc.)
2. Para probar cada metodo programado, se uso Postman, para facilitar las pruebas se agregado el archivo [PruebasP7](PruebasP7.json). Antes de realizar cualquier prueba se recomienda agregar al menos un par de elementos a la base de datos

**Objetos de la clase Category**

```bash
{
    "category": "Celulares",
    "acronym": "Cel"
}
```
   
```bash
{
    "category": "Musica",
    "acronym": "Mus"
}
```

**Objetos de la clase Product**

```bash
{
    "gtin": "Gtin1",
    "product": "Noquia",
    "description": "Noquia con 3 camaras",
    "price": "200",
    "stock": "20",
    "category_id": "1"
}
```

```bash
{
    "gtin": "Gtin2",
    "product": "Audifonos Zonyk",
    "description": "Zonyk AB300",
    "price": "100",
    "stock": "6",
    "category_id": "2"
}
```

```bash
{
    "gtin": "Gtin3",
    "product": "Bocinas Xiayomi",
    "description": "Xiayomi ABEC1",
    "price": "130",
    "stock": "10",
    "category_id": "2"
}
```

[Aplicaciones](http://localhost:8090/applications)

Creacion de DB

`CREATE TABLE category (category_id INT PRIMARY KEY, category VARCHAR(100), acronym VARCHAR(50), status INT);`

`CREATE TABLE product (product_id INT PRIMARY KEY, gtin VARCHAR(100), product VARCHAR(100), description VARCHAR(100), price DOUBLE, stock INT, category_id INT, status INT);`

`CREATE TABLE region (region_id INT PRIMARY KEY, region VARCHAR(100), status INT);`

`CREATE TABLE customer_image (customer_image_id INT PRIMARY KEY, customer_image VARCHAR(100));`

`CREATE TABLE customer (customer_id INT PRIMARY KEY, name VARCHAR(100), surname VARCHAR(100), date_birth DATE, rfc VARCHAR(15), mail VARCHAR(50), address VARCHAR(100), status INT, region_id INT, customer_image_id INT, FOREIGN KEY (region_id) REFERENCES region(region_id), FOREIGN KEY (customer_image_id) REFERENCES customer_image(customer_image_id));`

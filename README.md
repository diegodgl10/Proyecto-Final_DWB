# Proyecto 1

## Zamora Cruz Diego Arturo - 316249560

<br />

### El proyecto fue programado y probado con
- Spring Boot: 2.7.8
- Java: 11
- Eclipse IDE: 2022-09
- Postman: 10.10.9
- MySQL 8.0.32
  * base de datos: `dwb_proyecto`
  * usuario: `root`
  * password: `123456`

<br />

### Links
- Repositorio de [/config-data-dwb](https://github.com/diegodgl10/config-data-dwb)
- Aplicacion de [Spring Boot](http://localhost:8090/applications)

<br />

### Antes de la ejecución
- Crear una base de datos llamada `dwb_proyecto`
- Crear la tabla `category` con columnas:
    * *category_id* llave de tipo INT
    * *category* de tipo VARCHAR
    * *acronym* de tipo VARCHAR
    * *status* de tipo INT
- Crear la tabla `product` con columnas:
    * *product_id* llave de tipo INT
    * *gtin* de tipo VARCHAR
    * *product* de tipo VARCHAR
    * *description* de tipo VARCHAR
    * *price* de tipo DOUBLE
    * *stock* de tipo INT
    * *category_id* de tipo INT
    * *status* de tipo INT
- Crear la tabla `region` con columnas:
    * *region_id* llave de tipo INT
    * *region* de tipo VARCHAR
    * *status* de tipo INT
- Crear la tabla `customer_image` con columnas:
    * *customer_image_id* llave de tipo INT
    * *customer_image* de tipo VARCHAR
- Crear la tabla `customer` con columnas:
    * *customer_id* llave de tipo INT
    * *name* de tipo VARCHAR
    * *surname* de tipo VARCHAR
    * *date_birth* de tipo DATE
    * *rfc* de tipo VARCHAR
    * *mail* de tipo VARCHAR
    * *address* de tipo VARCHAR
    * *status* de tipo INT
    * *region_id* de tipo INT
    * *customer_image_id* de tipo INT
    * *region_id* referente a `region`*(region_id)*
    * *customer_image_id* referente a `customer_image`*(customer_image_id)*
- Crear la tabla `cart` con columnas:
    * *cart_id* llave de tipo INT
    * *rfc* de tipo VARCHAR
    * *gtin* de tipo VARCHAR
    * *quantity* de tipo INT
    * *status* de tipo INT
- Crear la tabla `invoice` con columnas:
    * *invoice_id* llave de tipo INT
    * *rfc* de tipo VARCHAR
    * *subtotal* de tipo DOUBLE
    * *taxes* de tipo DOUBLE
    * *total* de tipo DOUBLE
    * *created_at* de tipo DATE
    * *status* de tipo INT
- Crear la tabla `item` con columnas:
    * *item_id* llave de tipo INT
    * *invoice_id* de tipo INT
    * *gtin* de tipo VARCHAR
    * *quantity* de tipo INT
    * *unit_price* de tipo DOUBLE
    * *subtotal* de tipo DOUBLE
    * *taxes* de tipo DOUBLE
    * *total* de tipo DOUBLE
    * *status* de tipo INT

<br />

### Ejecucion del software
- Ejecutamos el programa con el software de su preferencia (spring tool suite, NetBeans, etc.)
- Para probar cada método programado, se usó Postman, por lo que se recomienda también usarlo.
- Se usó la aplicación de spring Boot para verificar el correcto arranque de las aplicaciones
- Para que arranquen correctamente las aplicaciones, se deben de ejecutar en un determinado orden, el orden que se usó es:
    * config-service
    * registry-service
    * gateway-service
    * admin-service
    * product
    * customer
    * invoice

<br />

### NOTA:
El requerimiento 5 no pudo ser terminado, al tratar de implementarlo únicamente entorpecía la ejecución de la aplicación, ya que no logre que funcionara correctamente, por lo que el código referente a ese punto no lo tengo implementado (lo menciono para no desperdiciar tiempo buscando el código referente a dicho punto). 😞
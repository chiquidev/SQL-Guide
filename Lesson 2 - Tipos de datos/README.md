Antes de proceder con la creación de tablas debemos conocer los tipos básicos de valores en una base de datos (SQL). Principalmente dividimos los tipos de datos en cinco grupos que se especifican a continuación:
* **Numerico** ej., INT, BIGINT, TINYINT, DECIMAL, etc.
* **Fechas y horas** ej., DATE, TIME, TIMESTAMP, YEAR, etc.
* **Cadenas** ej.,  VARCHAR, CHAR, ENUM, SET, BLOB, etc.
* **JSON** ej., JSON
* **Datos espaciales** representa la ubicación, el tamaño y la forma de un objeto en el planeta Tierra, como un edificio, un lago, una montaña o un municipio. MySQL también admite tipos de datos espaciales ej., GEOMETRY, POINT, etc.

Para nuestro ejemplo de la base de datos de Aerolineas usaremos el siguiente modelo de tabla, en este caso, de tarjetas de embarque:

| Nombre de la columna  | Tipo de columna    | 
|-----------------------|--------------------|
| Name                  | VARCHAR(20)        | 
| Surname               | VARCHAR(20)        | 
| Date                  | DATE               |
| Flight                | VARCHAR(20)        | 
| Gate                  | DECIMAL            | 

* *Nota: El número que se encuentra entre parentesis es la longitud del valor del texto que se insertará en este campo. El máximo es 65,535*. * 

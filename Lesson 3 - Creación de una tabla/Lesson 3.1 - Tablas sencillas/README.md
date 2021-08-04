A la hora de crear una tabla debemos especificar sus campos, nombre de la tabla, tipos de datos... Esto nos facilitará bastante trabajo, ya que... Si no tenemos nuestra tabla, ¿Cómo haremos las consultas?

* Sintaxis:
```
CREATE TABLE nombreTabla(
  columna1 <TipoDeDato> <Restrinciones>,
  columna2 <TipoDeDato> <Restrinciones>,
  columna3 <TipoDeDato> <Restrinciones>,
  <Key Principal o definiciones de Índice>
  );
```

---

Para la creación de nuestra tabla de ejemplo (Tarjetas de embarque) deberíamos de ejecutar el siguiente comando:
```sql
CREATE TABLE tarjetasEmbarque(
  Name    VARCHAR(20),
  Surname VARCHAR(20),
  Dates   DATE,
  Flight  VARCHAR(20),
  Gate    DECIMAL
  );
```

La sintaxis para definir una columna es tal que la siguiente:
```
nombreColumna tipoColumna [NOT NULL | NULL] [DEFAULT valorColumna]
```
---

Finalmente si nuestra tabla se ha creado de forma correcta podremos ejecutar el siguiente comando, y así comprobar un listado completo de las tablas de nuestra base de datos ([Creada en la lección Nº1](https://github.com/chiquidev/SQL-Guide/tree/main/Lesson1%20-%20Create%20Database)).

```
SHOW TABLES;

> Resultado esperado:
  +----------------------+
  | Tables_in_aerolines  |
  +----------------------+
  | tarjetasEmbarque     |
  +----------------------+
```

---

A su vez podemos inspeccionar y ver una descripción detallada de la tabla "tarjetasEmbarque" usando el comando `DESC`.

```
DESC tarjetasEmbarque;

> Resultado esperado:
  +--------------------+------------------+---------+-------+---------+-----------+
  | Field              |  Type            | Null    | Key   | Default |  Extra    |
  +--------------------+------------------+---------+-------+---------+-----------+
  | Name               |  varchar(20)     | YES     |       | Null    |           |
  | Surname	           |  varchar(20)     | YES     |       | Null    |           |
  | Dates 	           |  date            | YES     |       | Null    |           |
  | Flight 	           |  varchar(20)     | YES     |       | Null    |           |
  | Gate   	           |  decimal(10,0)   | YES     |       | Null    |           |
  +--------------------+------------------+---------+-------+---------+-----------+
  5 rows in set (0.00 sec)
```

El comando `DESC` nos muestra todas las columnas y metadatos de nuestra tabla, en este caso "tarjetasEmbarque", ofreciendonos valores colo el tipo de dato, si puede ser nulo...

Una de las ventajas que nos ofrece el sistema SQL es la posibilidad que nos añade para aplicar una mayor cantidad de restricciones a nuestros campos.

---

Para comenzar aplicando nuestra primera restricción procederemos a crear una `Primary Key`, que nos permitirá evitar insertar campos duplicados en nuestra tabla de SQL. En una posterior lección hablaremos acerca de las `Primarys Keys` de una forma un poco más detallada. En nuestro ejemplo con las tarjetas de embarque podríamos seleccionar los campos `Name`, `Surname` y `Flight` como campos primarios, pero existe la posibilidad de que más de un pasajero tengan el mismo nombre y apellido... Es por ello por lo que una sencilla solución sería agregar una nueva columna en la que se le asigne un ID de forma automática y que valla incrementando de forma progresiva cada vez que añadamos una nueva fila, dado que se asociará cada fila con un número diferente podemos estar seguros de que esa fila siempre se podrá identidicar de forma única con esa ID.

A s vez si creamos una nueva columna denominada ID y la designamos como `Primary Key` de la tabla tarjetasEmbarque deberíamos conocer el valor más alto de la columna ID, agregarle uno (+1) y entonces insertar el resultado como el ID en una nueva fila. Es por ello por lo que SQL nos ofrecé una característica denominada `AUTO_INCREMENT` que asigna automáticamente el siguiente entero de una secuencia en la columna ID de la nueva fila.

Listado de cosas que conocer antes de usar el valor `AUTO_INCREMENT`:
* La secuencia de `AUTO_INCREMENT` comienza en 1.
* Solo puede haber una columna marcada con `AUTO_INCREMENT`
* Este campo no puede tener un valor por defecto
* Esta columna deve de estar indexada.

La función de `AUTO_INCREMENT` no es portable a otras nuevas bases de datos, por lo que el contador se reseteará cuando borremos o portemos nuestra base de datos.

--- 

La siguiente restricción que queremos aplicar a nuestra tabla son los campos `NOT NULL`, que deshabilitará la función de insertar valores nulos en esos campos.

Imagina una situación en la que no conocemos el apellido de uno de nuestros pasajeros, en este caso podríamos usar la función `DEFAULT`, que nos permitirá insertar una constante por defecto en el campo marcado con esta función; esto nos permitirá y abrirá la posibilidad para hacer uso de la función `NOT NULL`, así siempre en el caso de que no conozcamos el apellido de un pasajero podamos insertar el campo sin necesidad de recibir errores.
* *Y sí, tanto NOT NULL como DEFAULT se pueden usar juntos*

```sql
CREATE TABLE tarjetasEmbarque(
  Id      INT         AUTO_INCREMENT,
  Name    VARCHAR(20) NOT NULL,
  Surname VARCHAR(20) NOT NULL DEFAULT "Unknown",
  Dates   DATE        NOT NULL,
  Flight  VARCHAR(20) NOT NULL,
  Gate    DECIMAL     NOT NULL,
  PRIMARY KEY (Id)
  );
```

Ahora contrastaremos la diferencía del uso del comando "DESC" en la lección anterior y en la actual:

```
> Resultado esperado en la lección 3.1:
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
  
  > Resultado esperado en la lección 3.2:
  +--------------------+------------------+---------+-------+---------+---------------+
  | Field              |  Type            | Null    | Key   | Default |  Extra        |
  +--------------------+------------------+---------+-------+---------+---------------+
  | ID                 |  int(11)         | NO      | Pri   | Null    | auto_incremet |
  | Name               |  varchar(20)     | NO      |       | Null    |               |
  | Surname	           |  varchar(20)     | NO      |       | Null    |               |
  | Dates 	           |  date            | NO      |       | Null    |               |
  | Flight 	           |  varchar(20)     | NO      |       | Null    |               |
  | Gate   	           |  decimal(10,0)   | NO      |       | Null    |               |
  +--------------------+------------------+---------+-------+---------+---------------+
  6 rows in set (0.00 sec)
  ```
  
  ---
  
  Finalmente destacar que podemos usar la función "IF EXISTS" a la hora de crear nuestra base de datos, permitiendonos crear la tabla sin efectos secundarios a la hora de crear nuestra tabla en el caso de que ya exista.
  
  
```sql
CREATE TABLE IF NOT EXISTS tarjetasEmbarque(
  Id      INT         AUTO_INCREMENT,
  Name    VARCHAR(20) NOT NULL,
  Surname VARCHAR(20) NOT NULL DEFAULT "Unknown",
  Dates   DATE        NOT NULL,
  Flight  VARCHAR(20) NOT NULL,
  Gate    DECIMAL     NOT NULL,
  PRIMARY KEY (Id)
  );
```

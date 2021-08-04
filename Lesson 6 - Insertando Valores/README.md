Al comenzar esta lección una de las cosas que nos planteamos es... ¿De que nos sirve una tabla si no tenemos valores insertados?... Pues creeme, es poco útil. 

Aquí aprenderemos el uso del estamento `INSERT`, y en la 7ª lección aprenderemos a obtener los valores que insertemos en esta lección mediante el estamento `SELECT`.

Para ello simplemente tendremos que usar una consulta de breves caracteres, como la que tendréis a continuación:

```sql
INSERT INTO table (col1, col2 … coln)
VALUES (val1, val2, … valn);
```

Como primera consulta insertaremos un pasajero en nuestra tabla tarjetas de embarque, como lo que os dejo a continuación:

```
INSERT INTO tarjetasEmbarque ( 
Name, Surname, Dates, Flight, Gate) 
VALUES ("Lorem Ipsum", "Dolor", "2021-08-04", "OKL018", 27);
> Resultado esperado: Query OK, 1 row affected (0.00 sec)
```

Esto nos devolverá el mensaje "Query OK, 1 row affected (0.00 sec)" si el valor se ha insertado de forma correcta

---

A su vez también podemos insertar más de una serie de valores en una misma consulta de SQL, escribiéndolo como os dejo a continuación:

```
INSERT INTO tarjetasEmbarque ( 
Name, Surname, Dates, Flight, Gate) 
VALUES 

("Josphine Ipsum", "Dolor", "2021-08-04", "OKL018", 27);
("Johan Ipsum", "Dolor", "2021-08-04", "OKL018", 27);
("Laura Ipsum", "Dolor", "2021-08-04", "OKL018", 27);

> Resultado esperado: Query OK, 3 rows affected (0.01 sec)
  Records: 3       Duplicates: 0        Warnings:0
```

Cuando insertamos múltiples tablas a la vez le damos la posibilidad a SQL de optimizar la consulta.

---

A su vez también podemos usar una consulta alternativa a la hora de insertar datos, ahorrandonos la necesidad de agregar los nombres de los ccampos donde queremos insertarlos:

```sql
INSERT INTO tarjetasEmbarque 
VALUES ("Carlos Ipsum", "DOLOR", "2021-08-04", "OKL018", 27);
> Resultado esperado: Query OK, 1 row affected (0.00 sec)
```

A destacar que si vamos a saltar los nombres de los campos debemos de seguir **la misma sintaxis** (El mismo orden) que los campos en los que se van a insertar.

---

A la hora de insertar un valor en SQL podemos saltar una columna, y decirle a SQL que lo inserte con el valor por defecto. Para ello usaremos la siguiente consulta de ejemplo;

```
INSERT INTO tarjetasEmbarque 
VALUES ("Carlos Ipsum", DEFAULT, "2021-08-04", "OKL018", 27);
> Resultado esperado: Query OK, 1 row affected (0.00 sec)
```

Esto habrá insertado lo siguiente en nuestra tabla de SQL:

```
+--------+----------------------+----------------------+----------------------+----------------------+----------------------+
| Id     | Name                 | Surname              | Dates                | Flight               |  Gate                |
+--------+----------------------+----------------------+----------------------+----------------------+----------------------+
| 1      | Carlos Ipsum         | Unknown              | 2021-08-04           | OKL018               | 27                   |
+--------+----------------------+----------------------+----------------------+----------------------+----------------------+
```

---

Finalmente una última consulta que podemos usar con otra sintaxis para insertar datos es la siguiente:

```
INSERT INTO tarjetasEmbarque 
SET Name="Marina Ipsum", Surname="Dolor", Date="2021-08-04", Flight="OKL018", Gate=27;
> Resultado esperado: Query OK, 1 row affected (0.00 sec)
```

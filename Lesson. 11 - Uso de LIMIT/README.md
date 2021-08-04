Por lo general, las tablas a lo largo del tiempo acaban teniendo cientos de miles o millones de filas y una consulta de selección puede devolver varios cientos de filas coincidentes. Esto puede llegar a ser muy problemático, ya que puede devolver miles de millones de resultados y acabar tirando el servidor y la conexión de la red (Creeme, me ha pasado)... La cláusula LIMIT nos permite restringir el número de filas devueltas del resultado de una consulta de selección. La sintaxis de esta consulta es la siguiente:

```
SELECT col1, col2, … coln
FROM table
WHERE col3 LIKE "%some-string%"
ORDER BY col3
LIMIT 10; // Solo se devolverán 10 filas.
```

---

Por ejemplo, supongamos que queremos obtener los tres primeros pasajeros del vuelo ordenados por su ID de usuario, para ello deberíamos de ejecutar l siguiente consulta:

```
SELECT Name, Surname from tarjetasEmbarque ORDER BY Id DESC LIMIT 3;
> Resultado esperado:
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | Id     | Name                 | Surname              | Dates                | Flight               |  Gate                |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | 1      | Lorem  Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 2      | Josphine Ipsum       | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 3      | Johan Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
```

* *Este tipo de funcionalidades suele ser muy útil para ordenar a usuarios en videojuegos por su "puntuación".*

---

A su vez, supongamos que queremos obtener los 4 pasajeros que van detrás de los tres primeros, para ello podríamos usar la funcionalidad OFFSET, esto lo realizamos con la siguiente consulta:

```
SELECT Name, Surname from tarjetasEmbarque ORDER BY Id DESC LIMIT 4 OFFSET 3;
> Resultado esperado:
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | Id     | Name                 | Surname              | Dates                | Flight               |  Gate                |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | 4      | Laura Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 5      | Carlos Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 6      | Carlos Ipsum         | Unknown              | 2021-08-04           | OKL018               | 27                   |
 | 7      | Marina Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
```

Aunque de forma alternativa también podríamos realizar la misma consulta con una sintaxis alternativa, tal y como se especifica a continuación:

```
SELECT Name, Surname from tarjetasEmbarque ORDER BY Id DESC LIMIT 3,4;
```

La sintaxis es la siguiente:

```
LIMIT <offset>, <numero_de_celdas_a_imprimir>;
```

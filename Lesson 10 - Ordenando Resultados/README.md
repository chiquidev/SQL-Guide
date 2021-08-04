Una de las funcionalidades más usadas del lenguaje SQL es el uso de la funcionalidad "ORDER BY", que nos permite ordenar los resultados de forma acorde a una variable en concreto. Supongamos que queremos ordenar a los pasajeros por orden alfabético, para ello podríamos ejecutar la siguiente consulta:

```
SELECT * FROM tarjetasEmbarque ORDER BY name
> Resultado esperado:
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | Id     | Name                 | Surname              | Dates                | Flight               |  Gate                |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | 5      | Carlos Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 6      | Carlos Ipsum         | Unknown              | 2021-08-04           | OKL018               | 27                   |
 | 2      | Josphine Ipsum       | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 3      | Johan Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 1      | Lorem  Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 4      | Laura Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 7      | Marina Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 7 rows in set (0.00 sec)
 ```
 
La cláusula ORDER BY va seguida del nombre de la columna en la que pretendemos ordenar, en este caso el nombre de los pasajeros, esta columna se llama clave de clasificación. De forma predeterminada, la clasificación no distingue entre mayúsculas y minúsculas y en orden ascendente.

---

A su vez, también podemos ordenarlos en orden descendente mediante el uso de la función "DESC", esto nos mostraría algo como lo siguiente:

```
SELECT * FROM tarjetasEmbarque ORDER BY name DESC;
> Resultado esperado:
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | Id     | Name                 | Surname              | Dates                | Flight               |  Gate                |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | 7      | Marina Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 4      | Laura Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 1      | Lorem  Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 3      | Johan Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 2      | Josphine Ipsum       | Dolor                | 2021-08-04           | OKL018               | 27                   | 
 | 6      | Carlos Ipsum         | Unknown              | 2021-08-04           | OKL018               | 27                   |
 | 5      | Carlos Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 7 rows in set (0.00 sec)
 ```
 
 ---
 
 Y también destacar que se pueden ordenar por más de un resultado, provocando así que en el caso de que dos resultados sean similares se siga otro orden, para esto simplemente deberíamos separar por "," los diferentes valores. A continuación se muestra un ejemplo:
 

```diff
SELECT * FROM tarjetasEmbarque ORDER BY surname, name;
 Resultado esperado:
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | Id     | Name                 | Surname              | Dates                | Flight               |  Gate                |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
+| 5      | Carlos Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 2      | Josphine Ipsum       | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 3      | Johan Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 1      | Lorem  Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 4      | Laura Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 7      | Marina Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
+| 6      | Carlos Ipsum         | Unknown              | 2021-08-04           | OKL018               | 27                   |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 7 rows in set (0.00 sec)
 ```
 
 Como se muestra en esta tabla todos los pasajeros tienen el mismo apellido, por lo que los ordena por su nombre. A su vez destacar que hay dos "Carlos Ipsum", y como uno de ellos tiene diferente apellido lo pone al final de la lista.
 
 
 

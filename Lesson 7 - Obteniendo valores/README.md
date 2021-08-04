Ahora que ya tenemos los valores insertados en nuestra tabla de `tarjetasEmbarque` ya podemos comenzar a obtenerla y consultarla, para ello ejecutaremos el estamento `SELECT` que nos devolverá una o todas las consultas de una tabla en concreto.

Nuestra primera consulta es bastante básica, y nos devolverá todos los registros de una tabla en concreto.

```
SELECT * from tarjetasEmbarque;
> Resultado esperado:
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | Id     | Name                 | Surname              | Dates                | Flight               |  Gate                |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | 1      | Lorem  Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 2      | Josphine Ipsum       | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 3      | Johan Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 4      | Laura Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 5      | Carlos Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 6      | Carlos Ipsum         | Unknown              | 2021-08-04           | OKL018               | 27                   |
 | 7      | Marina Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 7 rows in set (0.00 sec)
```

El comando lee todos los valores insertados en nuestra tabla, la sintaxis es muy simple, y os la dejo a continuación:

```
SELECT <columna/s> FROM <nombreTabla>
```

Detrás de la palabra "SELECT" le seguirá una serie de campos separados por una ",". Usando "*" nos devolverá un listado con todas las columnas de la tabla.

---

Ahora probaremos a hacer una consulta en la que solo obtengamos los nombres y apellidos de los diferentes pasajeros:
```
SELECT name, surname from tarjetasEmbarque;
> Resultado esperado:
 +----------------------+----------------------+
 | Name                 | Surname              | 
 +----------------------+----------------------+
 | Lorem  Ipsum         | Dolor                | 
 | Josphine Ipsum       | Dolor                | 
 | Johan Ipsum          | Dolor                | 
 | Laura Ipsum          | Dolor                |
 | Carlos Ipsum         | Dolor                | 
 | Carlos Ipsum         | Unknown              |
 | Marina Ipsum         | Dolor                | 
 +----------------------+----------------------+
 7 rows in set (0.00 sec)
```
* Las columnas se muestran siguiendo el orden de la ID, aunque en esta consulta no obtengamos ese campo.

---

A su vez también podemos filtrar las columnas usando el estamento "WHERE", esto nos devolverá las columnas que concuerden con un criterio especificado anteriormente. 

Para comprobar esto usaremos la siguiente consulta:
```
SELECT name, surname from tarjetasEmbarque WHERE name="Lorem Ipsum";
> Resultado esperado:
 +----------------------+----------------------+
 | Name                 | Surname              | 
 +----------------------+----------------------+
 | Lorem  Ipsum         | Dolor                | 
 +----------------------+----------------------+
 1 rows in set (0.00 sec)
```

--- 

La consulta WHERE nos permite usar algunos operadores con los campos números, los operadores son los siguientes:
| Operador | Propósito |
|----------|-----------|
| >        | Mayor que el operador |
| >=        | Mayor o igual que el operador |
| <        | Menor que el operador |
| <=        | Menor o igual que el operador |
| !=        | Diferente al operador |
| <>        | Diferente al operador |
| =        | Igual al operador |
| BETWEEN ... AND ...        | Entre un rango de valores |
| COALESCE()        | Devuelve el primer argunmento que no es nulo |
| GREATEST()	        | Devuelve el primer argunmento que no es nuloargumento con el valor más grande |
| IN	        | Si un valor está dentro de un conjunto de valores |
| INTERVAL	        | Devuelve el índice del argumento que es menor que el primer argumento |
| IS	        | Prueba un valor si es true/false |
| IS NOT 	        | Prueba un valor si no es true/false |
| IS NOT NULL	        | Prueba si un valor no es nulo |
| IS NULL	        | Prueba si un valor es nulo |
| LEAST()	        | Devuelve el argumento más pequeño |
| NOT BETWEEN ... AND ...	        | Comprueba si un valor no se encuentra entre un rango de valores |
| NOT IN()	        | Comprueba si un valor no se encuentra entre un set de valores |
| STRCMP()	        | Compara dos cadenas |






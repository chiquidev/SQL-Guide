A la hora de realizar consultas complejas una de las funcionalidades más usadas es la combinación de múltiples condiciones, la sintaxis que se debe de seguir para realizar esto es la siguiente:

```
SELECT col1, col2, … coln
FROM table
WHERE col3 LIKE "%cadena%"
AND
col4 = 55;
```

---

Para ello podemos usar el operador "AND" para por ejemplo, buscar todos los pasajeros por los que su nombre empieza por C o van a la gate 27.

```
SELECT * FROM Actors WHERE Name > "C" AND Gate = 27;
> Resultado esperado:
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | Id     | Name                 | Surname              | Dates                | Flight               |  Gate                |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | 5      | Carlos Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 6      | Carlos Ipsum         | Unknown              | 2021-08-04           | OKL018               | 27                   |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
```

---


A su vez también podemos combinar los operadores AND y OR, podiendo ejecutar querys como la siguiente:


```
SELECT * FROM Actors WHERE (Name > "C" AND Gate = 27) OR (Surname = "Dolor");
> Resultado esperado:
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | Id     | Name                 | Surname              | Dates                | Flight               |  Gate                |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | 1      | Lorem  Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 2      | Josphine Ipsum       | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 3      | Johan Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 4      | Laura Ipsum          | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 5      | Carlos Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 | 7      | Marina Ipsum         | Dolor                | 2021-08-04           | OKL018               | 27                   |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
```

En esta query aunque solo haya dos pasajeros por los que su nombre comience por "C" se muestran un mayor número de pasajeros debido a que su apellido es "Dolor".

---

Otro operador bastante útil a la hora de ejecutar consultas es el uso del operador "NOT", que lo que hace es negar un estamento boolean, por ejemplo, en la siguiente consulta obtendremos todos los pasajeros por los que su apellido no sea "Dolor".

```
SELECT * FROM Actors WHERE NOT(Surname = "Dolor");
> Resultado esperado:
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | Id     | Name                 | Surname              | Dates                | Flight               |  Gate                |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
 | 6      | Carlos Ipsum         | Unknown                | 2021-08-04           | OKL018               | 27                   |
 +--------+----------------------+----------------------+----------------------+----------------------+----------------------+
```

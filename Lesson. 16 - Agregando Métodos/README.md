En esta lección aprenderemos a agregar métodos a nuestras consultas de SQL. Un ejemplo de una consulta agregando un método es la siguiente:

```sql
SELECT Funcioón(col1)
FROM tabla;
```

---

Una de las funciones más utiles y que yo más uso es "COUNT", que nos permitirá contar el total de registros dee una tabla:

```
SELECT COUNT(*) FROM tarjetas Embarque;
> Resultado Esperado:
  +-----------------+
  | COUNT(*)        |
  +-----------------+
  |               7 |
  +-----------------+
  1 row in set (0.00 sec)
```

---

Usando la función "SUM" podemos sumar múltiples valores números de una columna, en nuestra tabla no tenemos nada que sumar, por lo que os dejaré la consulta:

```
SELECT SUM(Celda) FROM tabla;
```

---

Usando la función "AVG" podemos calcular una media de una serie de columnas, por lo que os dejaré la sintaxis:
```
SELECT AVG(Celda) FROM tabla;
```

---

También podemos encontrar el registro con una mayor cantidad en una tabla, y lo mismo con el que tiene menor cantidad, para ello deberíamos ejecutar las siguientes consultas:
```
SELECT MAX(Celda) FROM tabla;
SELECT MIN(Celda) FROM tabla;
```

Podemos eliminar las celdas de una tabla usando el estamento "DELETE", a destacar que al usar esta función eliminaremos **toda la fila**,  debido a que SQL no permite eliminar valores concretos con ete estamento. A continuación se muestra una sintaxis de ejemplo usando esta función:

```
DELETE FROM tabla
WHERE col3 > 5
ORDER BY col1
LIMIT 5;
```

---

Para comenzar solo eliminaremos una celda, para ello usaremos la función "WHERE" en la cual su funcionamiento es similar al de la función "SELECT". A continuación eliminaremos la celda en la que el apellido es "Unknown".

```sql
DELETE FROM tarjetasEmbarque WHERE Surname="Unknown"
> Resultado esperado: Query OK, 1 row affected (0.01 sec)
```

* *Ten en cuenta que SQL no tiene en cuenta las mayúsculas y minúsculas, por lo que aunque escribar "UNKNOWN" lo seguirá eliminando.*

---

A su vez, también podemos eliminar más de una celda a la vez, por ejemplo, podemos eliminar a "Carlos Ipsum Unknown" y a "Carlos Ipsum Dolor" desde una sola consulta, tal y como se muestra a continuación:

```sql
DELETE FROM tarjetasEmbarque WHERE Name="Carlos Ipsum";
> Resultado esperado: Query OK, 2 rows affected (0.01 sec)
``` 
* *Destacar que podemos usar la función ORDER BY y DELETE desde una misma consulta.*

---

Finalmente en el hipotético caso de que quisieramos eliminar todos los valores de una tabla (Uhh se me ponen los pelos de punta solo de pensarlo) para ello deberíamos usar la siguiente consulta:

```sql
DELETE FROM tarjetasEmbarque
> Resultado esperado: Query OK, 7 rows affected (0.01 sec)
```

* *Recuerda que lo que hemos eliminado son los valores, por lo que se podrá seguir accediendo a la tabla, solo que sin esos valores.*

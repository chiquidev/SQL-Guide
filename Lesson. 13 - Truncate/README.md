En la lección 12 se explica como eliminar todos los valores de una tabla, pero para ello existe un comando específico que nos facilita esta acción, la única diferencia respecto a DELETE es que esto no muestra el número total de filas afectadas, lo que hace que la consulta se ejecute bastante más rápido; a continuación se muestra un ejemplo de la sintaxis de esta.

```sql
TRUNCATE tabla;
```

---

En el caso de que quisieramos eliminar todos los pasajeros de la tabla tarjetasEmbarque simplemente deberíamos ejecutar una consulta de poco más de ocho caracteres:

```
TRUNCATE tarjetasEmbarque;
> Resultado esperado: Query OK, 0 rows affected (0.09 sec)
``` 

Para comprobar que se han eliminado todos los campos simplemente deberíamos ejecutar el comando:
```
SELECT * FROM tarjetasEmbarque;
> Resultado esperado: Empty set (0.00 sec)
```

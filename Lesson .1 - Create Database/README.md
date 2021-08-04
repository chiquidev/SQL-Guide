Comando para la creación de una base de datos.
```
CREATE DATABASE Aerolines;
> Resultado esperado: Query OK, 1 row affected (0.00 sec)
```

--- 
Si intentamos recrear una base de datos en SQL nos mostrará un error, por lo que podemos usar "IF NOT EXISTS" para crearla en el caso de que esta no exista, esto puede ser muy útil por si queremos crear un archivo shell para ejecutarlo y crear nuestra base de datos en una nueva máquina. 
```

CREATE DATABASE IF NOT EXISTS Aerolines;

> Resultado #1 - En el caso de que la base de datos no exista este la creará.
  Query OK, 1 row affected (0.00 sec)
> Resultado #2 - En el caso de que la base de datos sí exista este nos devolverá un error.
  ERROR 1049 (42000): Unknow database 'Aerolines'
```
---
Para ver un listado de las bases de datos de nuestro servidor SQL podemos usar el siguiente comando.

```
SHOW DATABASES;

> Resultado esperado:
+-----------------------+
| Databse               |
+-----------------------+
| Aerolines             |
+-----------------------+
```
---
Finalmente para la eliminación de una base de datos en nuestro servidor (Anteriormente creada) debemos ejecutar el siguiente comando:

``` 
DROP DATABASE MovieIndustry;

> Resultado Esperado:
  Query OK, 1 row affected (0.00 sec)
```

Una de las ventajas del uso de tablas SQL es la posibilidad que nos da del desarrollo de tablas temporales. Estas tablas solo se conservan mientras que dura la sesión de SQL, y se eliminan una vez que finaliza la sesión. Esto le permite al usuario que no le sea necesario limpiar de forma esplícita una tabla temporal.

Para la creación de una tabla temporal no es necesario tener conceptos avanzados acerca de SQL, simplemente debemos añadir una función detrás de "CREATE" en el comando de creación de nuestra tabla:

```
CREATE TEMPORARY TABLE nombreTabla(
  columna1 <TipoDeDato> <Restrinciones>,
  columna2 <TipoDeDato> <Restrinciones>,
  columna3 <TipoDeDato> <Restrinciones>,
  <Key Principal o definiciones de Índice>
  );
```

---

Para comprobar el funcionamiento de las tablas temporales os propongo un sencillo ejercicio, para comenzar creen una tabla temporal en vuestra sesión de SQL mediante el uso del siguiente comando:

```
CREATE TEMPORARY TABLE nombreTabla (Campo CHAR(20));
> Query OK, 0 rows affected (0.00 sec)
```

A continuación ejecuten el comando `DESC nombreTabla`, que os devolverá algo como esto:

```
DESC nombreTabla
> Resultado esperado:
  +--------------------+------------------+---------+-------+---------+-----------+
  | Field              |  Type            | Null    | Key   | Default |  Extra    |
  +--------------------+------------------+---------+-------+---------+-----------+
  | Campo              |  varchar(20)     | YES     |       | Null    |           |
  +--------------------+------------------+---------+-------+---------+-----------+
  1 row in set (0.00 sec)
```

Posteriormente cerramos nuestra sesión de SQL mediante el uso del comando `EXIT`, y volvemos a entrar. Una vez que salgamos y entremos de nuevo ejecutaremos el mismo comando que en el apartado anterior (DESC) que nos mostrará el siguiente error:

```
DESC nombreTabla
> ERROR 1146 (42502): Table 'nombreTabla.campo' doesn't exist.
```

Y... ¡Felicidades, has comprobado el uso de las tablas temporales!

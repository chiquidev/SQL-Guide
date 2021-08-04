Un set de caracteres nos define que caracteres puede almacenar nuestra tabla de SQL. Una tabla puede contener múltiples caracteres de lenguajes que no sean alfanuméricos, un ejemplo sencillo es el alfabeto friego, alemán, sueco, finlandés o español, que contienen caracteres como la `ñ` (Siii la ñ) o la ü.

Para ver que caracteres nos permite almacenar nuestro servidor de SQL podemos usar la siguiente query:

```
SHOW CHARACTER SET;
> No mostraré el resultado debido a que este puede variar en función de tu servidor.
```

Por defecto SQL usa el set de caracteres `latin-1`, que a su vez tiene asociado por defecto a `latin1_swedish_ci` el `ci` en el nombre nos muestra que este paquete contiene caracteres acentuados o con caracteres usados en Suecia por ejemplo...

Al igual ocurre lo mismo con las colecciones, y podemos verlas mediante el uso del siguiente comando:

```
SHOW COLLATION;
> No mostraré el resultado debido a que este puede variar en función de tu servidor.
```

* *Puedes inspeccionar los valores por defecto de tu servidor mediante el uso de la siguiente consulta:*

``` 
SHOW VARIABLES LIKE "c%";
> No mostraré el resultado debido a que este puede variar en función de tu servidor.
```

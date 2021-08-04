Una de las cosas más básicas en una base de datos es actualizar cierta información, para ello simplemente debemos usar la funcionalidad "UPDATE", a continuación os dejo la sintaxis de ejemplo:

```sql
UPDATE tabla
SET col1 = val1, col2 = val2, … coln = valn
WHERE <condición>
ORDER BY col5
LIMIT 5;
```

---

Supongamos que el vuelo "OKL018" se ha retrasado, y todos los pasajeros de este tendrán que irse al vuelo "ESP102", esto simplemente lo deberíamos de cambiar con una consulta, usando UPDATE:

```
UPDATE tarjetasEmbarque SET flight="ESP102"
```
*  *Esta consulta la podemos ejecutar ya que en nuestra tabla solo tenemos pasajeros de este vuelo, pero en el caso de que hubiese pasajeros de otros vuelos deberíamos ejecutar esta otra consulta:*

```
UPDATE tarjetasEmbarque SET flight="ESP102" WHERE flight="OKL018"
```

---

A su vez, supongamos que el avión solo tiene asientos para cinco personas, por lo que todos los pasajeros restantes deben irse al vuelo "CAN981" que tiene hueco para solo dos personas, para ello deberíamos usar la siguiente consulta:

```sql
UPDATE tarjetasEmbarque SET flight="CAN981" ORDER BY Id DESC LIMIT 2 OFFSET 5;
```

---

Y finalmente destacar que con el estamento "UPDATE" podemos cambiar múltiples valores, por ejemplo, si quieremos hacer que todos los pasajeros del vuelo "CAN981" se vayan al "ESP102" y a la puerta "11" simplemente deberíamos ejecutar la siguiente consulta:

```
UPDATE tarjetasEmbarque SET flight="ESP102", gate=11 WHERE flight="OKL018" 
```

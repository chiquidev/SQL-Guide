Cuando queremos obtener los valores que son distintos debemos añadir una palabra muy complicada, creeme, a nuestra consulta, esta consulta es "DISTINCT" y la sintaxis es la siguiente:

```sql
SELECT DISTINCT col1
FROM tabla;
```

* *Creeme, era complicado!!*

---

Por ejemplo, si queremos obtener un listado con todos los vuelos actuales simplemente deberíamos ejecutar la siguiente consulta:

```
SELECT DISTINCT flight from tarjetasEmbarque;
```

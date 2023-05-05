# SQL Direct




## Descripción
Connect to this PostgreSQL server and find the flag!

Additional details will be available after launching your challenge instance.

## Solución

- Entramos al servidor
- Con ayuda del comando \dt vemos las tablas de la BD
- Con la instrucción **SELECT * FROM flags;** vemos el contenido de la columna **flags**:
``` bash
┌──(kali㉿kali)-[~]
└─$ psql -h saturn.picoctf.net -p 64552 -U postgres pico
Contraseña para usuario postgres: 
psql (15.1 (Debian 15.1-1), servidor 15.2 (Debian 15.2-1.pgdg110+1))
Digite «help» para obtener ayuda.

pico=# 
pico=# 
pico=# \dt
        Listado de relaciones
 Esquema | Nombre | Tipo  |  Dueño   
---------+--------+-------+----------
 public  | flags  | tabla | postgres
(1 fila)

pico=# SELECT * FROM flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 filas)

pico=# 


```

## Bandera
picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| \dt |    List available tables|

## Referencias
- [PostgreSQL – Psql commands](https://www.geeksforgeeks.org/postgresql-psql-commands/)
- [Consulta de una tabla en SQL](https://learn.microsoft.com/es-es/sql/ssdt/how-to-view-and-edit-data-in-a-table?view=sql-server-ver16)

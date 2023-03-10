# picobrowser


## Descripción
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/26704/` ([link](https://jupiter.challenges.picoctf.org/problem/26704/)) or http://jupiter.challenges.picoctf.org:26704

## Pistas
- You don't need to download a new web browser

## Solución

- Entramos a la pagina web:   [link](https://jupiter.challenges.picoctf.org/problem/26704/)
 Ingresamos en la consola el comando curl en seguida del url de la página web, un flag al final del url, en seguida de la la instrucción que queremos que haga para entrar a la página web.
``` bash
kmonshe-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/26704/flag -H "User-Agent: picobrowser" | grep pico
         <!-- <strong>Title</strong> --> picobrowser!
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_e9b160d0}</code></p>
kmonshe-picoctf@webshell:~$
```

## Bandera
picoCTF{p1c0_s3cr3t_ag3nt_e9b160d0}

## Notas adicionales

| Comando | Descripción |
|------ | -------------- |
| curl | es una herramienta de línea de comandos de Linux que sirve para transferir datos hacia o desde un servidor con URL, utilizando cualquiera de los protocolos soportados (HTTP, FTP, POP3, IMAP, SMTP, SCP, SFTP, TFTP, TELNET, LDAP…). |
|-s| modo silencioso|
|-H|encabezado|



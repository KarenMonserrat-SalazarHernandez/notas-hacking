# Roboto Sans





## Descripción
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:64271/) out.

## Solución

- Se ingresa a la página web:
![[Pasted image 20230421221607.png]]

- Puede que el reto tenga que ver con algo que ver con **/robots.txt** :
![[Pasted image 20230421221804.png]]

- Ingresando con **/robots.txt** nos proporcionará algunos mensajes codificados en base64:
``` bash
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```

- Con ayuda de [CyberChef](https://gchq.github.io/CyberChef/) decodificamos los mensajes de base64:
![[Pasted image 20230421221947.png]]

- Al decodificar los menajes con base64 obtenemos una ruta donde se euncuentra la bandera:
![[Pasted image 20230421222048.png]]

## Bandera
picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}

## Referencias
- [CyberChef](https://gchq.github.io/CyberChef/)

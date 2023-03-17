# Scavenger Hun


## Descripción 
There is some interesting information hidden around this site [http://mercury.picoctf.net:5080/](http://mercury.picoctf.net:5080/). Can you find it?

## Pistas
- You should have enough hints to find the files, don't run a brute forcer.

## Solución

- Entramos al siguiente link: [http://mercury.picoctf.net:5080/](http://mercury.picoctf.net:5080/).
- Entramos al códifo fuente de la página web en la cual encontramos la primera parte de la bandera:
``` bash
<!-- Here's the first part of the flag: picoCTF{t -->
```
- Entre las lineas de código hay links a los que podemos entrar para seguir encontrando las otras parte de la bandera.
- Entramos al siguiente link: [http://mercury.picoctf.net:5080/mycss.css](http://mercury.picoctf.net:5080/mycss.css)
- Encontramos la parte 2 de la bandera:
``` bash
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
```
- Para seguir encontrando las otras partes de la bandera entramos al siguiente link: [http://mercury.picoctf.net:5080/robots.txt](http://mercury.picoctf.net:5080/robots.txt). para encontrar la parte 3 de la bandera:
``` bash
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?
```
- Entramos al siguiente link:  [http://mercury.picoctf.net:5080/.htaccess](http://mercury.picoctf.net:5080/.htaccess) para encontrar la parte 4 de la bandera:
``` bash
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
```
- Entramos al siguiente link: [http://mercury.picoctf.net:5080/.DS_Store](http://mercury.picoctf.net:5080/.DS_Store) para encontrar la parte 5 de la bandera:
``` bash
Congrats! You completed the scavenger hunt. Part 5: _35844447}
```

## Bandera
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_35844447}
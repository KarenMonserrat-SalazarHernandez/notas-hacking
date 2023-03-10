# where are the robots


## Descripción
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/36474/` ([link](https://jupiter.challenges.picoctf.org/problem/36474/)) or http://jupiter.challenges.picoctf.org:36474

## Pistas
- What part of the website could tell you where the creator doesn't want you to look?

## Solución

- Entramos a la pagina web:  [link](https://jupiter.challenges.picoctf.org/problem/36474/)
- Teniendo breve conocimiento sobre los archivos robots.txt realizamos lo siguiente para encontrar la bandera:
	- Despues del link de la pagina web agregamos robots.txt
``` bash
https://jupiter.challenges.picoctf.org/problem/36474/robots.txt
```
esta liga nos manda un mensaje:
``` bash
User-agent: *
Disallow: /477ce.html
```
esto quiere decir que no podemos entrar a la pagina 477ce.html original.

- Para encontrar la bandera accdemos a la pagína original:
``` bash
https://jupiter.challenges.picoctf.org/problem/36474/477ce.html 
```
De esta manera se accede a una parte de la página web que no estaba indexada en donde se encuentra la bandera.

## Bandera
picoCTF{ca1cu1at1ng_Mach1n3s_477ce}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| robots.txt | son archivos utilizados para favorecer la navegación de un algoritmo de búsqueda en un sitio web, orientando cuáles páginas deben ser indexadas en los buscadores y controlando las páginas a las que el robot del motor de búsqueda no debe acceder |


## Referencias
- [robots.txt](https://rockcontent.com/es/blog/robots-txt/)




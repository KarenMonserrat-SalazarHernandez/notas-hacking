# Bandit Level 7 → Level 8


## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth.**

## Datos de acceso al nivel 
- bandit7
- z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Solución
``` bash
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ wc data.txt
  98567  197133 4184396 data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
|     wc     | **muestra información estadística sobre un archivo, como el número de líneas, palabras y caracteres** |
| grep | mostrará en pantalla la totalidad de la línea/s que contiene/n la cadena de texto o palabra que estamos buscando. |


## Referencias
- [Ejemplos del comando WC: Contando el número de líneas, palabras y caracteres en Linux](https://itsfoss.com/es/comando-wc-linux/#:~:text=El%20comando%20wc%20muestra%20informaci%C3%B3n,de%20l%C3%ADneas%2C%20palabras%20y%20caracteres.&text=Trivia%3A%20wc%20significa%20word%20count,en%20espa%C3%B1ol%2C%20recuento%20de%20palabras.&text=El%20comando%20wc%20tiene%20las,s%C3%B3lo%20el%20n%C3%BAmero%20de%20l%C3%ADneas)
- [Uso del comando grep en Linux y UNIX con ejemplos](https://geekland.eu/uso-del-comando-grep-en-linux-y-unix-con-ejemplos/)

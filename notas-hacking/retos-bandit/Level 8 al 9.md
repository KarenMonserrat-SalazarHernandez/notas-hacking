# Bandit Level 8 → Level 9


## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once.

## Datos de acceso al nivel 
- bandit8
- TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Solución
``` bash
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ wc data.txt
 1001  1001 33033 data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| sort |  **ordena las líneas de un archivo (o su entrada estándar) y devuelve el resultado en su salida estándar**|
| uniq -u |comprueba las filas del archivo de texto repetidas, -u muestra las filas que solo se repiten una vez |

## Referencias
- [sort](https://www.ediciones-eni.com/open/mediabook.aspx?idR=cce9f7333cc7dd1baab4902c66c51606)
- [comando uniq ](https://www.w3big.com/es/linux/linux-comm-uniq.html#gsc.tab=0)

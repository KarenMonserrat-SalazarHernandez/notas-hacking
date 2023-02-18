# Bandit Level 9 → Level 10


## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso al nivel 
- bandit9
- EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Solución
``` bash
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ file data.txt
data.txt: data
bandit9@bandit:~$ strings data.txt | grep ==
c========== the
h;========== password
========== isT
n.E========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| strings | **Muestra las cadenas de caracteres imprimibles que contengan los ficheros**, útil para visualizar ficheros que no sean, o que no se sepa que son de texto plano. |

## Referencias
- [strings](https://francisconi.org/linux/comandos/strings#:~:text=Muestra%20las%20cadenas%20de%20caracteres,que%20son%20de%20texto%20plano.)

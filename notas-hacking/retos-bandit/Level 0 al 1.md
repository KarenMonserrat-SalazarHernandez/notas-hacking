# # Bandit Level 0 → Level 1


## Objetivo
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.  

## Datos de acceso al nivel 
bandit 0 - bandit 0


## Solución
``` bash 
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
bandit0@bandit:~$
```

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| cat | muestra el contenido de un archivo |
| ls | listar archivos |

## Referencias
- [# ls(1) — Linux manual page](https://man7.org/linux/man-pages/man1/ls.1.html)
- [# cat(1) — Linux manual page](https://man7.org/linux/man-pages/man1/cat.1.html)

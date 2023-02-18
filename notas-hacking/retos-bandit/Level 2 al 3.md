# Bandit Level 2 → Level 3

## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory.

## Datos de acceso al nivel 
- bandit 2
- rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
-  **spaces in this filename**

## Solución
``` bash 
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces in this filename
cat: space: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$
```

## Notas adicionales
El reto se puede resolver de dos maneras diferentes:

- Entrando con diagonales invertidas \\\  separando cada palabra del nombre del archivo
- Entrando por medio de comillas dobles "nombre del archivo"

## Referencias
- [Los nombres de archivo largos o las rutas de acceso con espacios requieren comillas](https://learn.microsoft.com/es-es/troubleshoot/windows-server/deployment/filenames-with-spaces-require-quotation-mark)


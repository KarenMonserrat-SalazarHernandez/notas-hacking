# Bandit Level 1 → Level 2

## Objetivo
The password for the next level is stored in a file called **-** located in the home directory.

## Datos de acceso al nivel 
- bandit 1
- NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
- -

## Solución
``` bash 
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ cat /home/bandit1/-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
```

## Notas adicionales
El reto se puede resolver de dos maneras diferentes:
- Entrando directamente con el comando cat ./-
- Entrando por medio de carpetas cat /home/bandit1/-

## Referencias
- [¿Cómo abrir un nombre de archivo con guiones "-" usando la terminal?](https://stackoverflow.com/questions/42187323/how-to-open-a-dashed-filename-using-terminal)



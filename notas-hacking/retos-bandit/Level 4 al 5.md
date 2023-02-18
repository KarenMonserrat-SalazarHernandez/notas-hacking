# Bandit Level 4 → Level 5


## Objetivo
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

## Datos de acceso al nivel 
- bandit4
- 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

## Solución
``` bash
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ cat ./-file00
T߼��B�������#6�Kt�3�
                     �6X��t���)bandit4@bandit:~/inhere$ file ./-file00
./-file00: data
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
bandit4@bandit:~/inhere$
```

## Notas adicionales

| Comando | Descripción |
|------ | -------------- |
| file ./* | muestra  el tipo de formato de los archivos|

## Referencias
- [# Comandos Linux file](https://www.hscripts.com/es/tutoriales/linux-commands/file.html)

# Bandit Level 32 → Level 33


## Objetivo
After all this `git` stuff its time for another escape. Good luck!

## Datos de acceso al nivel 
- bandit32
-  rmCBvG56y58BXzv98yZGdO7ATVL5dW8y

## Solución
``` bash

WELCOME TO THE UPPERCASE SHELL
>>
>> ls
sh: 1: LS: not found
>> whoami
sh: 1: WHOAMI: not found
>> $0
$ whoami
bandit33
$ pwd
/home/bandit32
$ ls
uppershell
$ file uppershell
uppershell: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=8864473908fa10566d408e55323058f479337c0b, for GNU/Linux 3.2.0, not stripped
$ cat /etc/passbandit33
cat: /etc/passbandit33: No such file or directory
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| whoami | proviene de la concatenación de las palabras en inglés ¿Who am I? que significa, ¿Quién soy? |


## Referencias
- [Comando whoami](https://denovatoanovato.net/comando-whoami/)

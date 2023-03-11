# First Grep


## Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Pistas
- grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solución
``` bash
──(kali㉿kali)-[~/Documentos/Primer Parcial ]
└─$ ls
file   
┌──(kali㉿kali)-[~/Documentos/Primer Parcial ]
└─$ cat file | grep pico
picoCTF{grep_is_good_to_find_things_dba08a45}   
┌──(kali㉿kali)-[~/Documentos/Primer Parcial ]
└─$ 

```

## Bandera
picoCTF{grep_is_good_to_find_things_dba08a45}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| grep | es un programa que buscará un conjunto dado de datos e imprimirá cada línea que contenga un patrón dado |

## Referencias
- [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)
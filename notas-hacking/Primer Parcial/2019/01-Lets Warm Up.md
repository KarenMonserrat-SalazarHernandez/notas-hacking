# Lets Warm Up


## Descripción
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

## Pistas
- Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

## Solución

En la terminal accedemos a python para encontrar la solución: 

``` bash
kmonshe-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> int(0x70)
112
>>> chr(112)
'p'
>>> chr(0x70)
'p'
>>> 
```

## Bandera
picoCTF{p}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| int | convierte a numero entero|
| char | convierte a caracter |

- Para obtener la bandera también se puede obtener directamente en un conversor de hexadecimal a Ascii.

## Referencias
- [Convertidor de texto hexadecimal a ASCII](https://www.rapidtables.org/convert/number/hex-to-ascii.html)

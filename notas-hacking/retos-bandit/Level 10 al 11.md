# Bandit Level 10 → Level 11


## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data.

## Datos de acceso al nivel 
- bandit 10
- G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solución
``` bash
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ echo "hola mundo"
hola mundo
bandit10@bandit:~$ echo "hola mundo" | base64
aG9sYSBtdW5kbwo=
bandit10@bandit:~$ echo  aG9sYSBtdW5kbwo= | base64 -d
hola mundo
bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ cat data.txt | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| echo | repite lo que se le encarga que repita |
| -d | permite decodificar datos|

| Concepto | Descripción |
|------ | -------------- |
| base64 | es un grupo de esquemas [de codificación de binario a texto](https://en.wikipedia.org/wiki/Binary-to-text_encoding "Codificación de binario a texto") que representan [datos binarios (más específicamente, una secuencia de](https://en.wikipedia.org/wiki/Binary_data "Datos binarios") [bytes](https://en.wikipedia.org/wiki/Byte "Byte") de 8 bits ) en secuencias de 24 [bits](https://en.wikipedia.org/wiki/Bit "Poco") que pueden representarse mediante cuatro dígitos Base64 de 6 bits. |

## Referencias
- [Explicamos el comando de Echo](https://www.ionos.mx/digitalguide/servidores/configuracion/linux-echo/)
- [Writeup - Wargame Bandit - Parte 2](https://www.w0lff4ng.org/wargame-bandit-2/)

# Bandit Level 12 → Level 13


## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!).

## Datos de acceso al nivel 
- bandit12
- JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## Solución
``` bash
bandit12@bandit:~$  xxd -r data.txt | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Tue Feb 21 22:02:52 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat |file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat |file -
/dev/stdin: gzip compressed data, was "data4.bin", last modified: Tue Feb 21 22:02:52 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat |file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$  xxd -r data.txt | zcat | bzcat | zcat | tar xO | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$  xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat |file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$  xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | file -
/dev/stdin: gzip compressed data, was "data9.bin", last modified: Tue Feb 21 22:02:52 2023, max compression, from Unix
bandit12@bandit:~$  xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat | file -
/dev/stdin: ASCII text
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:~$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| xxd| produce un volcado hexadecimal o binario de un archivo en varios formatos diferentes. También puede hacer lo contrario, convirtiendo de su formato de volcado hexadecimal a los datos originales
|zcat| descomprime una lista de archivos  (`.gz`) en la línea de comando o su `standard input` y escribe los datos sin comprimir en el `standard output`
|bzcat |es similar que zcat (descomprime todos los archivos indicados y lo envía `standard output`), pero de archivos `.bz2`
|tar xO| donde `x` es para extraer, y `O` es para extraer el archivo a un `standard output`
|file -| permite ver el formato del archivo descomprimido, donde el nombre de este es reemplazado por el símbolo `-`

| Concepto | Descripción |
|------ | -------------- |
|  Hex dump |muestra los ficheros en formato ASCII, octal, decimal y hexadecimal, según se lo especifiquemos. Si no se indica ningún fichero, los datos los lee de la entrada estándar

## Referencias
-  [Writeup - Wargame Bandit - Parte 2](https://www.w0lff4ng.org/wargame-bandit-2/)
- [Hex dump](https://www.fpgenred.es/GNU-Linux/hexdump_hd.html)
  
# Codebook



## Descripción
Run the Python script `code.py` in the same directory as `codebook.txt`.

-   [Download code.py](https://artifacts.picoctf.net/c/101/code.py)
-   [Download codebook.txt](https://artifacts.picoctf.net/c/101/codebook.txt)

## Pistas
- On the webshell, use `ls` to see if both files are in the directory you are in
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

- El desafío nos da dos archivos para descargar el cual dentro de esos dos  archivos esta la bandera.
- Se ejecuta el archivo con python:
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
 codebook.txt 
 code.py 
┌──(kali㉿kali)-[~/Descargas]
└─$ python code.py     
picoCTF{c0d3b00k_455157_7d102d7a}
└─$ 
```

## Bandera
picoCTF{c0d3b00k_455157_7d102d7a}


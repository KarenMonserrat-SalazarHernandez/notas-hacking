# fixme2.py



## Descripción
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/67/fixme2.py)

## Pistas
- Are equality and assignment the same symbol?
- To view the file in the webshell, do: `$ nano fixme2.py`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

 - El desafío nos da un archivo para descargar el cual dentro de el esta la bandera.
- Se ejecuta el archivo con python:
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
 fixme2.py 
┌──(kali㉿kali)-[~/Descargas]
└─$ python fixme2.py 
  File "/home/kali/Descargas/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
┌──(kali㉿kali)-[~/Descargas]
└─$ nano fixme2.py   
┌──(kali㉿kali)-[~/Descargas]
└─$ python fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}
┌──(kali㉿kali)-[~/Descargas]
└─$ 

```

- Se abre el archivo python con el editor nano para modificar el error.
- El problema estaba en la sentencia if.
- Cuando necesitamos comparar dos valores, usamos = =.  La asignación ocurre con solo =, como cuando queremos asignar un valor a una variable.
-  Finalmente, se ejecuta el programa con el siguiente comando.

```shell
python3 fixme1.py
```

- Se obtiene la bandera.

## Bandera
picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}


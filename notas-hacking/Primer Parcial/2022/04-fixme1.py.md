# fixme1.py



## Descripción
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/38/fixme1.py)

## Pistas
- Indentation is very meaningful in Python
- To view the file in the webshell, do: `$ nano fixme1.py`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

- El desafío nos da un archivo para descargar el cual dentro de el esta la bandera.
- Se ejecuta el archivo con python:
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls                     
 fixme1.py
┌──(kali㉿kali)-[~/Descargas]
└─$ python fixme1.py 
  File "/home/kali/Descargas/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
┌──(kali㉿kali)-[~/Descargas]
└─$ sudo nano fixme1.py                      
[sudo] contraseña para kali:
┌──(kali㉿kali)-[~/Descargas]
└─$ python fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}
┌──(kali㉿kali)-[~/Descargas]
└─$ 
```

- Se abre el archivo python con el editor nano para modificar el error.
- El problema es en laúltima línea. La sintaxis de Python es muy estricta con la sangría, lo que significa que los comandos deben sangrarse correctamente para que el programa se ejecute y sea lógicamente correcto.
- Finalmente, se ejecuta el programa con el siguiente comando.

```shell
python3 fixme1.py
```

- Se obtiene la bandera.

## Bandera
picoCTF{1nd3nt1ty_cr1515_09ee727a}



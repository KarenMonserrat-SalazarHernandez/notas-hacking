# convertme.py


## Descripción
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/30/convertme.py)

## Pistas
- Look up a decimal to binary number conversion app on the web or use your computer's calculator!
- The `str_xor` function does not need to be reverse engineered for this challenge.
- If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
- To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
- Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
- Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 convertme.py`

## Solución

- El desafío nos da un archivo para descargar el cual descarga un archivo llamado "convertme.py" dentro de ese archivo esta la bandera.
- Se ejecuta el archivo con python:
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
convertme.py
┌──(kali㉿kali)-[~/Descargas]
└─$ python convertme.py
If 21 is in decimal base, what is it in binary base?
Answer: 
``` 

- Se resuelve el problema que contiene el archivo:

``` bash
┌──(kali㉿kali)-[~]
└─$ python           
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(21)
'0b10101'
>>> 


```

- Se inserta la respuesta de la conversión de números:

``` bash
Answer: 10101
```

- Al insertar la respuesta y estar correcta, se muestra la bandera:

``` bash
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}
┌──(kali㉿kali)-[~/Descargas]
└─$ 
```

## Bandera
picoCTF{4ll_y0ur_b4535_762f748e}


# runme.py



## Descripción
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/86/runme.py)

## Pistas
- If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
- To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
- Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
- Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!

## Solución

- El desafío nos da un archivo para descargar el cual descarga un archivo llamado "runme.py" dentro de ese archivo esta la bandera. 
- Con el comando cat mostramos el contenido de dicho archivo:
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
runme.py 
┌──(kali㉿kali)-[~/Descargas]
└─$ cat runme.py   
#!/usr/bin/python3
################################################################################
# Python script which just prints the flag
################################################################################

flag ='picoCTF{run_s4n1ty_run}'
print(flag)
┌──(kali㉿kali)-[~/Descargas]
└─$ 
```

## Bandera
picoCTF{run_s4n1ty_run}


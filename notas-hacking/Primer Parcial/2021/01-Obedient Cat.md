# Obedient Cat


## Descripción
This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag).

## Pistas
- Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.
- To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag`
- $ man cat

## Solución

- El desafío nos da un enlace para descargar el cual descarga un archivo llamado "flag" dentro de ese archivo esta la bandera. 
- Con el comando cat mostramos el contenido de dicho archivo:
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
 flag                                          
┌──(kali㉿kali)-[~/Descargas]
└─$ cat flag                   
picoCTF{s4n1ty_v3r1f13d_1a94e0f9}
┌──(kali㉿kali)-[~/Descargas]
└─$ 

```

## Bandera
picoCTF{s4n1ty_v3r1f13d_1a94e0f9}


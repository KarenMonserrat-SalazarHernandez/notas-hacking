# Glitch Cat



## Descripción
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 53933`

## Pistas
- ASCII is one of the most common encodings used in programming
- We know that the glitch output is valid Python, somehow!
- Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

## Solución

 - El desafío nos da un comando para conectarnos a un servidor usando netacad:
``` bash
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 53933
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
┌──(kali㉿kali)-[~]
└─$ python3
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print('picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}')
picoCTF{gl17ch_m3_n07_a4392d2e}
>>> 
```

- La bandera está incompleta, contiene algunos caracteres ASCII. 
- Se convierten los caracteres usando python3
-  Se imprime la cadena de la bandera para obtener la bandera adecuada.

## Bandera
picoCTF{gl17ch_m3_n07_a4392d2e}



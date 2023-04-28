# Pixelated



## Descripción
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png)

## Pistas
- [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
- Think of different ways you can "stack" images

## Solución

- Haciendo uso de la herramienta *imagemagick* empalmamos las 2 imagenes que nos da el reto para obtener la bandera:
``` bash
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ ls                     
scrambled1.png  scrambled2.png  
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ convert scrambled1.png scrambled2.png -compose Add -composite flag.png
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ open flag.png
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ 


```

## Bandera 
picoCTF{2a4d45c7}



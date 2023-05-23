# Flags




## Descripción
What do the [flags](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png) mean?

## Pistas
- The flag is in the format PICOCTF{}

## Solución

- Vemos el tipo de archivo y es una imagen png:

``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls    
flag.png
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ file flag.png 
flag.png: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ open flag.png 
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ 


``` 

- Con ayuda de  código bandera internacional encontramos la bandera:
![[Pasted image 20230519230613.png]]

## Bandera 
picoCTF{F1AG5AND5TUFF}


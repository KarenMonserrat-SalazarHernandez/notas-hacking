# The numbers



## Descripción
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

## Pistas
- The flag is in the format PICOCTF{}

## Solución

- Se descarga el archivo
- Vemos que es un archivo PNG y lo abrimos para ver que hay en la imagen 
``` bash
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ ls
the_numbers.png
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ file the_numbers.png 
the_numbers.png: PNG image data, 774 x 433, 8-bit/color RGB, non-interlaced
                                                                                                                                                            
└─$ open the_numbers.png 
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ 


```

![[Pasted image 20230420005150.png]]
- Contenido de la imagen

Para poder encontrar la bandera nos ayudamos del alfabeto numerado:

![[Pasted image 20230420005516.png]]


## Bandera 
picoCTF{Thenumbersmason}


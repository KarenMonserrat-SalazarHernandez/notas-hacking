# hideme



## Descripción

## Pistas
-

## Solución
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
flag.png   keyz
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas]
└─$ unzip flag.png  
Archive:  flag.png
warning [flag.png]:  39739 extra bytes at beginning or within zipfile
  (attempting to process anyway)
   creating: secret/
  inflating: secret/flag.png         
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
flag.pngz       secret
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas]
└─$ cd secret         
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/secret]
└─$ ls
flag.png
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/secret]
└─$ open flag.png
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/secret]
└─$ 
```



## Bandera
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_d55982e8}
# plumbing


## Descripción
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.

## Pistas
- Remember the flag format is picoCTF{XXXX}
- What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)

## Solución
``` bash
                                                                                                        
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 7480
Not a flag either
Again, I really don't think this is a flag
This is defintely not a flag
Not a flag either
This is defintely not a flag
Not a flag either
Not a flag either
Not a flag either
Again, I really don't think this is a flag
I don't think this is a flag either
This is defintely not a flag
This is defintely not a flag
This is defintely not a flag
I don't think this is a flag either
.
.
.
I don't think this is a flag either
Again, I really don't think this is a flag
Not a flag either
Again, I really don't think this is a flag
Not a flag either
                                                                                                         
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 7480 >> flagout.txt
                                                                                                         
┌──(kali㉿kali)-[~]
└─$ ls
Descargas  Documentos  Escritorio  flagout.txt  Imágenes  Música  Plantillas  Público  Vídeos
                                                                                                         
┌──(kali㉿kali)-[~]
└─$ cat flagout.txt | grep pico
picoCTF{digital_plumb3r_06e9d954}
                                                                                                         
┌──(kali㉿kali)-[~]
└─$ 
```

## Bandera
picoCTF{digital_plumb3r_06e9d954}

## Referencias
- [kind](http://www.linfo.org/pipes.html)



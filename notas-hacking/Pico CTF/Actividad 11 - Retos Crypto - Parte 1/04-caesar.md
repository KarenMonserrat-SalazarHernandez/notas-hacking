# caesar




## Descripción
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/6385b895dcb30c74dbd1f0ea271e3563/ciphertext).

## Pistas
- caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)

## Solución

- Descargamos el archivo
- Vemos el contenido del archivo
``` bash
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ ls
ciphertext  
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ cat ciphertext 
picoCTF{dspttjohuifsvcjdpoabrkttds}                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ 

```

- Con ayuda de  - [CyberChef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,25)&input=ZHNwdHRqb2h1aWZzdmNqZHBvYWJya3R0ZHM)  encontramos la Bandera al aplicar ROT:
![[Pasted image 20230420011705.png]]
- Aplicando 25 veces ROT encontramos la Bandera

## Bandera 
picoCTF{crossingtherubiconzaqjsscr}

## Referencias
 - [CyberChef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,25)&input=ZHNwdHRqb2h1aWZzdmNqZHBvYWJya3R0ZHM)

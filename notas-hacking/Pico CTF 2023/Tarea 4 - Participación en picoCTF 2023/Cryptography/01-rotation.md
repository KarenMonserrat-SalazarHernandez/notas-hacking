# rotation



## Descripción
You will find the flag after decrypting this file Download the encrypted flag [here](https://artifacts.picoctf.net/c/386/encrypted.txt).


## Pistas
- Sometimes rotation is right

## Solución

- El archivo encrypted.txt contiene lo siguiente:
``` bash
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
 encrypted.txt
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ cat encrypted.txt                                                                    
xqkwKBN{z0bib1wv_l3kzgxb3l_4k71n5j0}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ 

```

- Con ayuda de la herramienta ROT de  [CyberChef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,18)&input=eHFrd0tCTnt6MGJpYjF3dl9sM2t6Z3hiM2xfNGs3MW41ajB9DQo) rotamos las veces necesarias para enconraer la bandera.
- Se realizaron 18 rotaciones para encontrar la bandera:
![[Pasted image 20230330194022.png]]

## Bandera
picoCTF{r0tat1on_d3crypt3d_4c71f5b0}


## Referencias
- [CyberChef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,18)&input=eHFrd0tCTnt6MGJpYjF3dl9sM2t6Z3hiM2xfNGs3MW41ajB9DQo)
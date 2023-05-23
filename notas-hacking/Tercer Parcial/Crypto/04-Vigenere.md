# Vigenere




## Descripción
Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/158/cipher.txt) using this key "CYLAB".

## Pistas
- https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher

## Solución


``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls
cipher.txt
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ cat cipher.txt 
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_cc82272b}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ 
``` 

- Con ayuda de [CyberChef](https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('CYLAB')&input=cmdub0RWRHtPME5VX1dRM19HMUczTzNUM19BMUFIM1NfY2M4MjI3MmJ9DQo) encontramos la bandera:
![[Pasted image 20230520002201.png]]

## Bandera 
picoCTF{}

## Referencias
- [CyberChef](https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('CYLAB')&input=cmdub0RWRHtPME5VX1dRM19HMUczTzNUM19BMUFIM1NfY2M4MjI3MmJ9DQo)

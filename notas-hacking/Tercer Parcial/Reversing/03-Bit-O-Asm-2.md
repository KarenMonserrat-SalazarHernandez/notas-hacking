# Bit-O-Asm-2



## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).

## Pistas
- `PTR`'s or 'pointers', reference a location in memory where values can be stored.

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls
disassembler-dump0_b.txt
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ cat disassembler-dump0_b.txt
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ 


``` 

- Podemos observar que el unico registro con eax es el mov con el registro [rbp-0x4] en hexa, por lo que nos regresamos a donde se encuentra la instrucción y la dirección es 0x9fe1a en hexa para convertirlo a decimal se uso [ CONVERTIR HEXADECIMAL A DECIMAL](https://www.to-convert.com/es/numero/convertir-hexadecimal-a-decimal.php) donde 0x9fe1a hexa = 654874  decimal por lo tanto la bandera es picoCTF{654874}.

## Bandera 
picoCTF{654874}

## Referencias
- [CONVERTIR HEXADECIMAL A DECIMAL](https://www.to-convert.com/es/numero/convertir-hexadecimal-a-decimal.php)



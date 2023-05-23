# Bit-O-Asm-1



## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).

## Pistas
- As with most assembly, there is a lot of noise in the instruction dump. Find the one line that pertains to this question and don't second guess yourself!

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls
disassembler-dump0_a.txt
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ cat disassembler-dump0_a.txt                                                                  
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ 

``` 

- Podemos observar que el unico registro con eax es el mov con el registro 0x30 en hexa, para convertirlo a decimal se uso [ CONVERTIR HEXADECIMAL A DECIMAL](https://www.to-convert.com/es/numero/convertir-hexadecimal-a-decimal.php) donde 0x30 hexa = 48 decimal por lo tanto la bandera es picoCTF{48}.

## Bandera 
picoCTF{48}

## Referencias
- [CONVERTIR HEXADECIMAL A DECIMAL](https://www.to-convert.com/es/numero/convertir-hexadecimal-a-decimal.php)

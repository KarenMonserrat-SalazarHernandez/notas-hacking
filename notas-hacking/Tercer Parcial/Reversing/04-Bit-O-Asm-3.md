# Bit-O-Asm-3



## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

## Pistas
- Not everything in this disassembly listing is optimal.

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls
disassembler-dump0_c.txt
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ cat disassembler-dump0_c.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ 

``` 


- Podemos observar que ahora tenemos varios registro con eax igual con diferentes intrucciones .
 ``` bash
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc] -- eax = 0x9fe1a --linea +15
<+32>:    imul   eax,DWORD PTR [rbp-0x8] -- eax = 0x9fe1a * 0x4 = 0x27F868 --linea +22
<+36>:    add    eax,0x1f5               -- eax = 0x9fe1a * 0x4 = 0x27F868 + 0x1f5 = 0x27FA5D 
<+41>:    mov    DWORD PTR [rbp-0x4],eax -- eax = 0x0x27FA5D, [rbp-0x4] = 0x27FA5D
<+44>:    mov    eax,DWORD PTR [rbp-0x4  -- eax = 0x27FA5D
 ```


- Una vez realizado las intrucciones obtuvimos que eax = 0x27FA5D en hexa  para convertirlo a decimal se uso [ CONVERTIR HEXADECIMAL A DECIMAL](https://www.to-convert.com/es/numero/convertir-hexadecimal-a-decimal.php) donde 0x27FA5D hexa = 2619997  decimal por lo tanto la bandera es picoCTF{2619997}.

## Bandera 
picoCTF{2619997}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| imul | multiplicación |
| add | suma |
| mov | mover |


## Referencias
- [CONVERTIR HEXADECIMAL A DECIMAL](https://www.to-convert.com/es/numero/convertir-hexadecimal-a-decimal.php)



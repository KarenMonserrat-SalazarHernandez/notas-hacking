# Bit-O-Asm-4




## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

## Pistas
- Don't tell anyone I told you this, but you can solve this problem without understanding the compare/jump relationship.
- Of course, if you're really good, you'll only need one attempt to solve this problem.

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls
disassembler-dump0_d.txt
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ cat disassembler-dump0_d.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ 

``` 


- Podemos observar que ahora tenemos varios registro con eax igual con diferentes intrucciones .
 ``` bash
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a --  eax = 0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710  -- compara si 0x9fe1a es menor 0x2710
<+29>:    jle    0x55555555514e <main+37>    -- como no se cumple se va a la sig. instrucción --linea +31
<+31>:    sub    DWORD PTR [rbp-0x4],0x65    --  eax = 0x9fe1a - 0x65 = 0x9FDB5
<+35>:    jmp    0x555555555152 <main+41>    --  salta a la --linea +41
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]     -- se mueve a la --linea +15 
											 -- eax = 0x9FDB5
 ```


- Una vez realizado las intrucciones obtuvimos que eax = 0x9FDB5 en hexa  para convertirlo a decimal se uso [ CONVERTIR HEXADECIMAL A DECIMAL](https://www.to-convert.com/es/numero/convertir-hexadecimal-a-decimal.php) donde eax = 0x9FDB5 hexa = 654773  decimal por lo tanto la bandera es picoCTF{654773}.

## Bandera 
picoCTF{654773}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| cmp | compara |
| sub | resta |
| jmp | salto |


## Referencias
- [CONVERTIR HEXADECIMAL A DECIMAL](https://www.to-convert.com/es/numero/convertir-hexadecimal-a-decimal.php)



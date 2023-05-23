# GDB baby step 2




## Descripción
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).

## Pistas
- You could calculate `eax` yourself, or you could set a breakpoint for after the calculcation and inspect `eax` to let the program do the heavy-lifting for you.

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls             
debugger0_b
                                                                                                                                                              
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ gdb debugger0_b
GNU gdb (Debian 13.1-2) 13.1
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_b...
(No debugging symbols found in debugger0_b)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
   0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x1e0da,-0x4(%rbp)
   0x000000000040111c <+22>:    movl   $0x25f,-0xc(%rbp)
   0x0000000000401123 <+29>:    movl   $0x0,-0x8(%rbp)
   0x000000000040112a <+36>:    jmp    0x401136 <main+48>
   0x000000000040112c <+38>:    mov    -0x8(%rbp),%eax
   0x000000000040112f <+41>:    add    %eax,-0x4(%rbp)
   0x0000000000401132 <+44>:    addl   $0x1,-0x8(%rbp)
   0x0000000000401136 <+48>:    mov    -0x8(%rbp),%eax
   0x0000000000401139 <+51>:    cmp    -0xc(%rbp),%eax
   0x000000000040113c <+54>:    jl     0x40112c <main+38>
   0x000000000040113e <+56>:    mov    -0x4(%rbp),%eax
   0x0000000000401141 <+59>:    pop    %rbp
   0x0000000000401142 <+60>:    ret
End of assembler dump.
(gdb) 

``` 

- Podemos observar que ahora tenemos varios registro con eax igual con diferentes intrucciones .
 ``` bash
   0x0000000000401115 <+15>:    movl   $0x1e0da,-0x4(%rbp)  -- eax =  [rbp-0x4] = 0x1e0da
   0x000000000040111c <+22>:    movl   $0x25f,-0xc(%rbp)    -- eax = [rbp-0xc]= 0x25f
   0x0000000000401123 <+29>:    movl   $0x0,-0x8(%rbp)      -- eax = [rbp-0x8]= 0x0
   0x000000000040112a <+36>:    jmp    0x401136 <main+48>   -- salta a la linea --linea +48
   0x000000000040112c <+38>:    mov    -0x8(%rbp),%eax      -- eax = [rbp-0x8] = 0x0
   0x000000000040112f <+41>:    add    %eax,-0x4(%rbp)      -- [rbp-0x4]= 0x1e0da + eax
   0x0000000000401132 <+44>:    addl   $0x1,-0x8(%rbp)      -- eax = [rbp-0x8] + 1 = 0x1
   0x0000000000401136 <+48>:    mov    -0x8(%rbp),%eax      -- eax = [rbp-0x8]    
   0x0000000000401139 <+51>:    cmp    -0xc(%rbp),%eax      -- compara si eax es < [rbp-0xc] 
   0x000000000040113c <+54>:    jl     0x40112c <main+38>   -- regresa a --linea +38
   0x000000000040113e <+56>:    mov    -0x4(%rbp),%eax
 ```


- Una vez realizado las intrucciones nos dimos cuenta que no se acaba con una iteración
- Deben de pasar 607 veces para terminar 
- Con ayuda de la formula de **Gauss** encontraremos la bandera
- sum  =  n(n+1)/2
- sum  =  ((1+606)/2)*606
- sum = 183921
-  eax = 183921 + [rbp-0x4] 
-  eax =183921 + 0x1e0da
-  eax = 183921 + 123098
-  eax = 307019
-  Por lo tanto la bandera es picoCTF{307019}.

## Bandera 
picoCTF{307019}

## Referencias
- [CONVERTIR HEXADECIMAL A DECIMAL](https://www.to-convert.com/es/numero/convertir-hexadecimal-a-decimal.php)
- [Gauss](https://www.saberespractico.com/curiosidades/gauss-suma-100-primeros-numeros-naturales/)



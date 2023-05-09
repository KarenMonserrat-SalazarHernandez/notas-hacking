# GDB Test Drive - picoCTF 2022




## Descripción
Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/87/gdbme).Here's the test drive instructions:

-   `$ chmod +x gdbme`
-   `$ gdb gdbme`
-   `(gdb) layout asm`
-   `(gdb) break *(main+99)`
-   `(gdb) run`
-   `(gdb) jump *(main+104)`

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ ls
gdbme
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ file gdbme         
gdbme: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=15cc42b7d1ba7d200593c720e2d9fd2e757fccca, for GNU/Linux 3.2.0, not stripped
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ cat gdbme              
@@@@�▒▒▒��   xx�-�=�=���-�=�=�888 XXXDDS�td888 P�td   LLQ�tdR�td�-�=�=xx/lib64/ld-linux-x86-64.so.2GNU�GNU�B�Ѻ} �� ���.u��GNU
                                                                                                                             �
                                                                                                                              (��e�mf� +
                                                                                                                                        9T� � $?2▒E"libc.so.6__stack_chk_failputcharstrdupstrlenstdoutfputssleep__cxa_finalize__libc_start_mainfreeGLIBC_2.4GLIBC_2.2.5_ITM_deregisterTMCloneTable__gmon_start___ITM_r@u▒iterTu�@�?�?��?eii   �?
 �?�?�?�?�?�?
�?
                                                                                                                                                    
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ chmod +x gdbme         
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ ./gdbme         
^C
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ gdb -q gdbme      
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) disassemble main
Dump of assembler code for function main:
   0x00000000000012c7 <+0>:     endbr64
   0x00000000000012cb <+4>:     push   %rbp
   0x00000000000012cc <+5>:     mov    %rsp,%rbp
   0x00000000000012cf <+8>:     sub    $0x50,%rsp
   0x00000000000012d3 <+12>:    mov    %edi,-0x44(%rbp)
   0x00000000000012d6 <+15>:    mov    %rsi,-0x50(%rbp)
   0x00000000000012da <+19>:    mov    %fs:0x28,%rax
   0x00000000000012e3 <+28>:    mov    %rax,-0x8(%rbp)
   0x00000000000012e7 <+32>:    xor    %eax,%eax
   0x00000000000012e9 <+34>:    movabs $0x4c75257240343a41,%rax
   0x00000000000012f3 <+44>:    movabs $0x4362383846336235,%rdx
   0x00000000000012fd <+54>:    mov    %rax,-0x30(%rbp)
   0x0000000000001301 <+58>:    mov    %rdx,-0x28(%rbp)
   0x0000000000001305 <+62>:    movabs $0x6630624760433530,%rax
   0x000000000000130f <+72>:    movabs $0x4e67646635656666,%rdx
   0x0000000000001319 <+82>:    mov    %rax,-0x20(%rbp)
   0x000000000000131d <+86>:    mov    %rdx,-0x18(%rbp)
   0x0000000000001321 <+90>:    movb   $0x0,-0x10(%rbp)
   0x0000000000001325 <+94>:    mov    $0x186a0,%edi
   0x000000000000132a <+99>:    call   0x1110 <sleep@plt>
   0x000000000000132f <+104>:   lea    -0x30(%rbp),%rax
   0x0000000000001333 <+108>:   mov    %rax,%rsi
   0x0000000000001336 <+111>:   mov    $0x0,%edi
   0x000000000000133b <+116>:   call   0x1209 <rotate_encrypt>
   0x0000000000001340 <+121>:   mov    %rax,-0x38(%rbp)
   0x0000000000001344 <+125>:   mov    0x2cc5(%rip),%rdx        # 0x4010 <stdout@@GLIBC_2.2.5>
   0x000000000000134b <+132>:   mov    -0x38(%rbp),%rax
   0x000000000000134f <+136>:   mov    %rdx,%rsi
   0x0000000000001352 <+139>:   mov    %rax,%rdi
   0x0000000000001355 <+142>:   call   0x10f0 <fputs@plt>
--Type <RET> for more, q to quit, c to continue without paging--
   0x000000000000135a <+147>:   mov    $0xa,%edi
   0x000000000000135f <+152>:   call   0x10c0 <putchar@plt>
   0x0000000000001364 <+157>:   mov    -0x38(%rbp),%rax
   0x0000000000001368 <+161>:   mov    %rax,%rdi
   0x000000000000136b <+164>:   call   0x10b0 <free@plt>
   0x0000000000001370 <+169>:   mov    $0x0,%eax
   0x0000000000001375 <+174>:   mov    -0x8(%rbp),%rcx
   0x0000000000001379 <+178>:   xor    %fs:0x28,%rcx
   0x0000000000001382 <+187>:   je     0x1389 <main+194>
   0x0000000000001384 <+189>:   call   0x10e0 <__stack_chk_fail@plt>
   0x0000000000001389 <+194>:   leave
   0x000000000000138a <+195>:   ret
End of assembler dump.
(gdb) 
(gdb) 
(gdb) layout asm
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ 

``` 

-  Realizando los pasos que nos da el reto se obtiene la bandera:
![[Pasted image 20230509134351.png]]



## Bandera 
picoCTF{d3bugg3r_dr1v3_7776d758}


# GDB baby step 1



## Descripción
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).

## Pistas
- gdb is a very good debugger to use for this problem and many others!
- `main` is actually a recognized symbol that can be used with gdb commands.

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls
asciiftw  debugger0_a
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ cat debugger0_a             
@@@@�▒▒▒����   00�-�=�= (.>>�888 XXXDDS�td888 P�td   <<Q�tdR�td�-�=�=/lib64/ld-linux-x86-64.so.2GNU�GNU���,��
                                                                                                             <�
                                                                                                               ��}\��GNU��e�m8 ▒T c 
                                                                                                                                    "libc.so.6__cxa_finalize__libc_start_mainGLIBC_2.2.5_ITM_deregisterTMCloneTable__gmon_start___ITM_registerTMCloneTableu▒i      ,� @�?�?�?�?�?��H�H��/H��t��H���5�/��%�/����%�/D��1�H�=��r/��H�=�/H��/H9�tH�N/H��t �����H�=i/H�5b/H)�H��H��?H��H�H��tH�%/H����fD�����=%/u+UH�=/H��t
                                                                                                H�=/�)����d�����.]������w�����UH���}�H�u��B]Ð��AWL�=�,AVI��AUI��ATA��UH�-�,SL)�H������H��t1��L��L��D��A��H��H9�u�H�[]A\A]A^A_�ff.������H�H��8���l,����<���T%����<��������zRx
                                                                                                                ����/D$4����F▒J
M                                                                                                                              �?▒:*3$"\����tq���E�C
D�h���eF�I▒�E �E(�D0�H8�G@n8A0A(B B▒B����� �
��▒����o�X�
}
 ▒�?    ������o����o���o����o@GCC: (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0▒8X|��� �
 

0@�  @ �=�=>�?@▒@��
                   p�!�7▒@F�=m y�=������,!����=�>��=� ��?�

�▒ ^ @6@�=\@i @� �@e�▒▒@b@/�▒@�)�@� �"crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.8061__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entrydebugger0_a.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_ITM_deregisterTMCloneTable_edata__libc_start_main@@GLIBC_2.2.5__data_start__gmon_start____dso_handle_IO_stdin_used__libc_csu_init__bss_startmain__TMC_END___ITM_registerTMCloneTable__cxa_finalize@@GLIBC_2.2.5.symtab.strtab.shstrtab.interp.note.gnu.property.note.gnu.build-id.note.ABI-tag.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.init.plt.plt.got.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.data.bss.comment▒▒#886XX$I|| W���o��a
                                                                                                                                                         ��▒iXX}q���o��
�  �  <�@ @ �����>.��?��@@00+@0▒        6�8
                                                                                                                                                                                                      
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ gdb debugger0_a 
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
Reading symbols from debugger0_a...
(No debugging symbols found in debugger0_a)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   %rbp
   0x000000000000112e <+5>:     mov    %rsp,%rbp
   0x0000000000001131 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000001134 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000001138 <+15>:    mov    $0x86342,%eax
   0x000000000000113d <+20>:    pop    %rbp
   0x000000000000113e <+21>:    ret
End of assembler dump.
(gdb) 
``` 

- Podemos observar que tenemos solo un registro eax  con la intrucción mov, pero ya contiene el registro 
 ``` bash
  0x0000000000001138 <+15>:    mov    $0x86342,%eax
 ```


- Por lo que eax = 0x86342 en hexa  para convertirlo a decimal se uso [ CONVERTIR HEXADECIMAL A DECIMAL](https://www.to-convert.com/es/numero/convertir-hexadecimal-a-decimal.php) donde 0x86342 hexa = 549698  decimal por lo tanto la bandera es picoCTF{549698}.

## Bandera 
picoCTF{549698}

## Referencias
- [CONVERTIR HEXADECIMAL A DECIMAL](https://www.to-convert.com/es/numero/convertir-hexadecimal-a-decimal.php)



# Reverse




## Descripción
Try reversing this file? Can ya? I forgot the password to this [file](https://artifacts.picoctf.net/c/273/ret). Please find it for me?

## Solución
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
 disk.flag.img.gz   enc_flag        Forensic                              'LibreOffice_7.4.4_Linux_x86-64_deb(1).tar.gz'   Obsidian-1.1.16.AppImage   ret
 email-export.eml   encrypted.txt   LibreOffice_7.4.4.2_Linux_x86-64_deb   LibreOffice_7.4.4_Linux_x86-64_deb.tar.gz       readmycert.csr
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ cat ret             
@@@@�▒▒▒((UU   ���-�=�=x��-�=�=�888 XXXDDS�td888 P�td� � � DDQ�tdR�td�-�=�=hh/lib64/ld-linux-x86-64.so.2GNU�GNUd�m�8���
                                                                                                                       �"�/P~;\�GNU
�
�e�m ▒0MF� 
           � 7"libc.so.6__isoc99_scanfputs__stack_chk_failprintf__cxa_finalizestrcmp__libc_start_mainGLIBC_2.7GLIBC_2.4GLIBC_2.2.5_ITM_deregisterTMCloneTabiu▒igmons��@�?�?�?�?_reg�?terTMCloneTableii
�H�=���.��H�=�.H��.H9�tH��.H��t������H�=�.H�5�.H)�H��H��?H��H�H��tH��.H����fD�����=�.u+UH�=b.H��t%/D����%
                                                                                                 H�=f.������d����].]������w�����UH��H��`dH�%(H�E�1�H�picoCT����H�E�H��������H���B�����u▒H�=�ce55fulH�E�H�U�H�_d7b14d4H�E�H�=�
������H�M�dH3    H�=�
             %(t�������f.���AWL�=�*AVI��AUI��ATA��UH�-�*SL)�H������H��t1��L��L��D��A��H��H9�u�H�[]A\A]A^A_�ff.������H�H��Enter the password to unlock this file: %sYou entered: %s
Password correct, please see flag: picoCTF{3lf_r3v3r5ing_succe55ful_d7b14d43}Access denied@|���t����������<���\%����,��������4zRx
                                                                                                                                ����/D$4���`F▒J
                                                                                                                                               �?▒:*3$"\8���t0���P�Q����E�C
D�8���eF�I▒�E �E(�D0�H8�G@n8A0A(B B▒B�`�����
H�▒����o���
�
 ▒�?x�� ������o����o���o����o�=0@P`@GCC: (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0▒8X|���   �
�
 �
 ���H � � �=�=�=▒�?@▒@�
                       @!�7▒@F�=m�y�=�������!����=��=��=�� �▒�?�
                                                                @ � @.@@
                                                                        HGcw�@�� @� ��e�▒▒@��/�▒@���@) C"crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.8061__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entryret.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_ITM_deregisterTMCloneTableputs@@GLIBC_2.2.5_edata__stack_chk_fail@@GLIBC_2.4printf@@GLIBC_2.2.5__libc_start_main@@GLIBC_2.2.5__data_startstrcmp@@GLIBC_2.2.5__gmon_start____dso_handle_IO_stdin_used__libc_csu_init__bss_startmain__isoc99_scanf@@GLIBC_2.7__TMC_END___ITM_registerTMCloneTable__cxa_finalize@@GLIBC_2.2.5.symtab.strtab.shstrtab.interp.note.gnu.property.note.gnu.build-id.note.ABI-tag.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.rela.plt.init.plt.got.plt.sec.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.data.bss.comment▒▒#886XX$I|| W���o��a
�  �� � D�� ������=�-��?�@0q���o��~���o�����▒�B��x▒�  `������P���e�HH
                         @00+@0x▒       �6_9▒                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ strings ret | grep pico
picoCTF{H
Password correct, please see flag: picoCTF{3lf_r3v3r5ing_succe55ful_d7b14d43}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ 
```

## Bandera
picoCTF{3lf_r3v3r5ing_succe55ful_d7b14d43}
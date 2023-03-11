# Wave a flag


## Descripción
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm) has extraordinarily helpful information...

## Pistas
- This program will only work in the webshell or another Linux computer.
- To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm`
- Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`
- -h and --help are the most common arguments to give to programs to get more information from them!
- Not every program implements help features like -h and --help.

## Solución

- El desafío nos da un enlace para descargar un archivo ejecutable ELF de 64 bits llamado "warm".
- Con el comando cat mostramos el contenido de dicho archivo:
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
warm
┌──(kali㉿kali)-[~/Descargas]
└─$ cat warm
ELF>�@8"@8      @"!@@@�888

 XX/lib64/ld-linux-x86-64.so.2GNUGNUPk{�5
.��F[K                                   g*��
       -&g v "libc.so.6putsprintf__cxa_finalizestrcmp__libc_start_mainGLIBC_2.2.5_ITM_deregisterTMCloneTa � � � � �� � � H�H�}_registerTMCloneTableu▒i   ?�
 H��t��H���5*
 �%,
 @�%*
 h������%"
 h������%▒
 h������%2
cH�=���� �DH�=��PTL��H�
 UH�
]��f.�]�@f.�H�=� H��t    H�5�    UH)�H��H��H��H��?H�H��t▒H��     H��t
                                                                     ]��f�]�@f.��=y      u/H�=W  UH��t
                                                                                                      H�=����H����Q       ]����fDUH��]�f���UH��H���}�H�u��}�uH�=�������KH�E�H�H�H�5�H���������uH�=��i����H�E�H�H�H��H�=:��X������DAWAVI��AUATL�%F UH�-F SA��I��L)�H�H�������H��t 1��L��L��D��A��H��H9�u�H�[]A\A]A^A_Ðf.���H�H��Hello user! Pass me a -h to learn what I can do!-hOh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_616f7182}I don't know what '%s' means! I do know what -h means though!
<��������▒���X"�����������0zRx
                             ����+zRx
                                    $8���@F▒J
l                                            �?▒;*3$"DP��\R���qA�C
D|����eB�B▒�E �B(�H0�H8�M@r8A0A(B B▒B�������
���o���                                     `
�
 �� GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.0�q�
                                               �w�q8�x�.in���i��%��▒    M�b     k��     j��     d��▒    S��      ?��(
��0
T�8
�@
��H
@�P
!�X
R`
�
Xh
�
 bp
Vbt
px
�F�
rT�
I▒^�
�n�
%{�
�-��
�.��
�/��
�0��
�2-�
^3b�
b5t�
�X  �>▒���      ��R
▒         �n
8�/?��@��A��P�X��X��X▒▒b
                        ������q�9*b�9��%
                                        ;
                                         I$
                                           >
                                            $
                                             >
                                             I&I
                                               :
                                                ;
:
 ;
  I8
:
 ;I8
    :
     ;
!I/   I
   <4:
8#TT 1tt$D���o�N
i@��'��30t�@▒� ▒��▒V���^�*� >  

```

Dentro del archivo ejecutable viene la bandera, pero hay que buscarla entre todos los caracteres, y para evitar eso por medio de comandos obtenemos solo la bandera:

``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ./warm
zsh: permiso denegado: ./warm
```

Permiso denegado, podría ser que no tiene permiso de ejecución. Para dar permiso entrar

``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ chmod +x warm
┌──(kali㉿kali)-[~/Descargas]
└─$ sudo ./warm  
[sudo] contraseña para kali: 
Hello user! Pass me a -h to learn what I can do!
┌──(kali㉿kali)-[~/Descargas]
└─$ sudo ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_616f7182}
┌──(kali㉿kali)-[~/Descargas]
└─$ 
```

## Bandera
picoCTF{b1scu1ts_4nd_gr4vy_616f7182}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| chmod +x | agrega privilegios de ejecución al usuario propietario actual del archivo especificado |

## Referencias
- [chmod +x](https://linuxtect.com/what-is-chmod-x-command-in-linux/)


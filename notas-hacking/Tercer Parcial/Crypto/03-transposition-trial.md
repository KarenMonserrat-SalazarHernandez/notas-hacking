# transposition-trial




## Descripción
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.Download the corrupted message [here](https://artifacts.picoctf.net/c/193/message.txt).

## Pistas
- Split the message up into blocks of 3 and see how the first block is scrambled

## Solución

- El archivo contiene la bandera en desorden:
``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls
message.txt 
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ cat message.txt 
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ nano flag.py             
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ nano flag.txt
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ python3 flag.py               
  File "/home/kali/Descargas/3P/flag.py", line 7
    flag += mensaje[i + 2] + [i:i + 2]
                               ^
SyntaxError: invalid syntax
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ nano flag.py   
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ python3 flag.py
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ 
``` 

- Se crea un archivo .py para ordenar la bandera:
``` bash
mensaje = "heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7"

flag = ""
for i in range(0, len(mensaje), 3):
        flag += mensaje[i + 2] + mensaje[i:i + 2]
print(flag)
``` 

## Bandera 
picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}


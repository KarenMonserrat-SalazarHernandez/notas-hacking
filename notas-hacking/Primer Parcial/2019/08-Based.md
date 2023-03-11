# Based



## Descripción
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.

## Pistas
- I hear python can convert things.
- It might help to have multiple windows open.

## Solución
``` bash
                                                                                                         
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 29221
Let us see how data is stored
computer
Please give the 01100011 01101111 01101101 01110000 01110101 01110100 01100101 01110010 as a word.
...
you have 45 seconds.....

Input:
computer
Please give me the  154 141 155 160 as a word.
Input:
lamp
Please give me the 6c616d70 as a word.
Input:
lamp
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_00a975ff}
                                                                                                         
┌──(kali㉿kali)-[~]
└─$ 

```

Se hace la conversión de las cadenas de numeros (binarios, octales, hexadecimales) a texto por medio de conversores para ingresarlos a la ternimal y obtener la bandera.

## Bandera
picoCTF{learning_about_converting_values_00a975ff}

## Referencias
- [Conversor de Código Binario a Texto](https://es.convertbinary.com/de-binario-a-texto/)
- [Conversor octal a texto](https://photo333.com/octal-to-text-es.php)
- [Convertidor de texto hexadecimal a ASCII](https://www.rapidtables.org/convert/number/hex-to-ascii.html)

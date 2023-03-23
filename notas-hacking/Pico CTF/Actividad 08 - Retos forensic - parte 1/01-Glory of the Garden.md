# Glory of the Garden



## Descripción
This [garden](https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg) contains more than it seems.


## Pistas
What is a hex editor?

## Solución

- El reto nos da una imagen en el cual viene la bandera oculta
- Al ver el contenido de la imagen se observa que contiene caracteres raros
- Se abre un editor hexadecimal para poder encontrar la bandera con más facilidad, pero hay que buscarla dentro de todos los caracteres
- Para evitar estar buscando la bandera dentro de todos los caracteres, usamos el comado string seguido de un grep para poder mostrar la bandera directamente:
``` bash
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ ls
garden.jpg
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ file garden.jpg                                                                                            
garden.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 72x72, segment length 16, baseline, precision 8, 2999x2249, components 3
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ open garden.jpg 
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ cat garden.jpg 
����JFIFHH��
            XICC_PROFILE
                        HLinomntrRGB XYZ �      1acspMSFTIEC sRGB���-HP  cprtP3desc�lwtpt�bkptrXYZ▒gXYZ,bXYZ@dmndTpdmdd��vuedL�view�$lumi�meas
                                                                                                                                              $tech0
                                                                                                                                                    rTRC<
                                                                                                                                                        gTRC<
bTRC<
    textCopyright (c) 1998 Hewlett-Packard CompanydescsRGB IEC61966-2.1sRGB IEC61966-2.1XYZ �Q�XYZ XYZ o�8��XYZ b���▒�XYZ $����descIEC http://www.iec.chIEC http://www.iec.chdesc.IEC 61966-2.1 Default RGB colour space - sRGB.IEC 61966-2.1 Default RGB colour space - sRGBdesc,Reference Viewing Condition in IEC61966-2.1,Reference Viewing Condition in IEC61966-2.1view��_.���
                                                            \�XYZ L     VPW�meas�sig CRT curv
%+28>ELRY`gnu|������������������������������
                              &/8AKT]gqz������������
+:IXgw��������'7HYj{�������+=Oat�������             !-8COZfr~���������� -;HUcq~���������
.
.
.

                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ 1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c1;2c
1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c1: command not found
2c: command not found
                                                                                                                                                
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ hexeditor garden.jpg 
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ strings garden.jpg -n 20 | grep pico
Here is a flag "picoCTF{more_than_m33ts_the_3y3657BaB2C}"
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ 

```

## Bandera
picoCTF{more_than_m33ts_the_3y3657BaB2C}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| string | convierte número en una cadena de caracteres|


## Referencias
- [String](https://help.highbond.com/helpdocs/analytics/141/scripting-guide/es/Content/lang_ref/functions/r_string.htm#:~:text=STRING(%20)%20convierte%20n%C3%BAmero%20en%20una,retorno%20desde%20el%20lado%20izquierdo)





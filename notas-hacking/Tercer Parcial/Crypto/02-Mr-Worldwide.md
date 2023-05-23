# Mr-Worldwide




## Descripción
A musician left us a [message](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). What's it mean?

## Solución

- El archivo de texto contiene coordenadas:

``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls
message.txt  picker-IV  picker-IV.c
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ cat message.txt 
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ 
``` 

- Con ayuda de [MAPS](https://www.google.com/maps/@41.015137,28.9769551,17z?authuser=0) encontramos los lugares:
``` bash
picoCTF{
(35.028309, 135.753082)    Nakanocho, Kamigyō-ku, Kioto, Prefectura de Kioto 602-0958, Japón
(46.469391, 30.740883)     Odesa, Ucrania, 65000
(39.758949, -84.191605)    Dayton, OH 45402, Estados Unidos
(41.015137, 28.979530)     Hoca Paşa, 34110 Fatih/Provincia de Istambul, Turquía
(24.466667, 54.366669)     Hazza  Bin Zayed The First St - Al Manhal - Abu Dhabi - Emiratos Árabes Unidos
(3.140853, 101.693207)     Room 11, Level 2, Bangunan Sulaiman, Jalan Sultan Hishamuddin, 50000 Kuala Lumpur, Malasia
_
(9.005401, 38.763611)      Kirkos, Adís Abeba, Etiopía
(-3.989038, -79.203560)    Av. Nueva Loja, Loja, Ecuador  
(52.377956, 4.897070)      Martelaarsgracht 5, 1012 TM Amsterdam, Países Bajos
(41.085651, -73.858467)    4 lighthouse landing, Sleepy Hollow, NY 10591, Estados Unidos
(57.790001, -152.407227)   Kodiak, AK 99615, Estados Unidos
(31.205753, 29.924526)     Faculty Of Engineering, Al Azaritah WA Ash Shatebi, Bab Sharqi, Alexandria Governorate 5423021, Egipto
} 

picoCTF{
Kioto
Odesa
Dayton
Istambul
Abu Dhabi
Kuala Lumpur
_
Adís Abeba
Loja
Amsterdam
Sleepy Hollow
Kodiak
Alexandria
}

picoCTF{KODIAK_ALASKA}
```

 La bandera es la inicial de cada ubicación
 
## Bandera 
picoCTF{KODIAK_ALASKA}


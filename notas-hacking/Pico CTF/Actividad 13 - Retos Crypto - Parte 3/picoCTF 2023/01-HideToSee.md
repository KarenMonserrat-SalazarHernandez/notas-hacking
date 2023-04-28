# HideToSee




## Descripción
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/235/atbash.jpg).

## Pistas
- Download the image and try to extract it.

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ ls
atbash.jpg
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ exiftool atbash.jpg 
ExifTool Version Number         : 12.49
File Name                       : atbash.jpg
Directory                       : .
File Size                       : 51 kB
File Modification Date/Time     : 2023:04:27 13:10:42-06:00
File Access Date/Time           : 2023:04:27 13:11:08-06:00
File Inode Change Date/Time     : 2023:04:27 13:10:49-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Image Width                     : 465
Image Height                    : 455
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 465x455
Megapixels                      : 0.212
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ steghide extract -sf atbash.jpg 
Anotar salvoconducto: 
anot� los datos extra�dos e/"encrypted.txt".
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ cat encrypted.txt   
krxlXGU{zgyzhs_xizxp_92533667}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$  
```

![[Pasted image 20230427141745.png]]

## Bandera 
picoCTF{atbash_crack_92533667}

## Referencias
- [CyberChef](https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfOTI1MzM2Njd9DQo)


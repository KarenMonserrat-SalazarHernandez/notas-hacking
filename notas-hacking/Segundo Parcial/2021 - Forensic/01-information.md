# information



## Descripción
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg)

## Pistas
- Look at the details of the file
- Make sure to submit the flag as picoCTF{XXXXX}

## Solución

- Se descarga el archivo
- Vemos que tipo de archivo es y su contenido
``` bash
┌──(kali㉿kali)-[~/Descargas/Segundo Parcial]
└─$ ls
cat.jpg
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Segundo Parcial]
└─$ file cat.jpg                
cat.jpg: JPEG image data, JFIF standard 1.02, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 2560x1598, components 3
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Segundo Parcial]
└─$ open cat.jpg  
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Segundo Parcial]
└─$ cat cat.jpg   
����JFIF��0Photoshop 3.08BIMtPicoCTF��
                                      �http://ns.adobe.com/xap/1.0/<?xpacket begin='' id='W5M0MpCehiHzreSzNTczkc9d'?>
<x:xmpmeta xmlns:x='adobe:ns:meta/' x:xmptk='Image::ExifTool 10.80'>
<rdf:RDF xmlns:rdf='http://www.w3.org/1999/02/22-rdf-syntax-ns#'>

 <rdf:Description rdf:about=''
  xmlns:cc='http://creativecommons.org/ns#'>
  <cc:license rdf:resource='cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9'/>
 </rdf:Description>

 <rdf:Description rdf:about=''
  xmlns:dc='http://purl.org/dc/elements/1.1/'>
  <dc:rights>
   <rdf:Alt>
    <rdf:li xml:lang='x-default'>PicoCTF</rdf:li>
   </rdf:Alt>
  </dc:rights>
 </rdf:Description>
</rdf:RDF>
</x:xmpmeta>

▒▒
�>
"���
!"1AQ2aq#B��R���3b�$Cr��S��     4c�%DT���▒Us�&5t��6Ed�'�7F��!1"AQa2q���B���#R���3bCr$S��
                                                                                        ?��������������������������������A
Ò#�@(��                                                                                                                   ▒�C�#�)�����
       �*K�Z▒�|
               u��H0f�BbT�
                          rL|׃#U▒��6�J��8���JA*K��
                                                  s܅V��N۱*K�H#�u@�Q�h#���EԻ�
.
.
.
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Segundo Parcial]
└─$ exiftool cat.jpg  
ExifTool Version Number         : 12.49
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2023:04:20 16:47:24-06:00
File Access Date/Time           : 2023:04:20 16:48:03-06:00
File Inode Change Date/Time     : 2023:04:20 16:47:31-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1  
┌──(kali㉿kali)-[~/Descargas/Segundo Parcial]
└─$ 

```

Dentro del contenido de la imagen encontramos una serie de numeros en base64

```
cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
```

Con ayuda de [CyberChef](https://gchq.github.io/CyberChef/) aplicamos base64 para encontrar la bandera:
![[Pasted image 20230420180335.png]]

## Bandera
picoCTF{the_m3tadata_1s_modified}

## Referencias
-  [CyberChef](https://gchq.github.io/CyberChef/)




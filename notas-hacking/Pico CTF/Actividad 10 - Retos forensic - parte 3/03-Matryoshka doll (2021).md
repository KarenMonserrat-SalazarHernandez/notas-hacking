
# Matryoshka doll



## Descripción
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg)

## Pistas
- Wait, you can hide files inside files? But how do you find them?
- Make sure to submit the flag as picoCTF{XXXXX}

## Solución



``` bash
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ ls
capture.pcap  dolls.jpg  picopico.key
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ file dolls.jpg   
dolls.jpg: PNG image data, 594 x 1104, 8-bit/color RGBA, non-interlaced
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ open dolls.jpg 
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ exiftool dolls.jpg 
ExifTool Version Number         : 12.49
File Name                       : dolls.jpg
Directory                       : .
File Size                       : 652 kB
File Modification Date/Time     : 2023:03:30 21:25:30-06:00
File Access Date/Time           : 2023:03:30 21:25:57-06:00
File Inode Change Date/Time     : 2023:03:30 21:25:57-06:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 594
Image Height                    : 1104
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Profile Name                    : ICC Profile
Profile CMM Type                : Apple Computer Inc.
Profile Version                 : 2.1.0
Profile Class                   : Display Device Profile
Color Space Data                : RGB
Profile Connection Space        : XYZ
Profile Date Time               : 2020:06:09 12:08:45
Profile File Signature          : acsp
Primary Platform                : Apple Computer Inc.
CMM Flags                       : Not Embedded, Independent
Device Manufacturer             : Apple Computer Inc.
Device Model                    : 
Device Attributes               : Reflective, Glossy, Positive, Color
Rendering Intent                : Perceptual
Connection Space Illuminant     : 0.9642 1 0.82491
Profile Creator                 : Apple Computer Inc.
Profile ID                      : 0
Profile Description             : Display
Profile Description ML (hr-HR)  : LCD u boji
Profile Description ML (ko-KR)  : 컬러 LCD
Profile Description ML (nb-NO)  : Farge-LCD
Profile Description ML (hu-HU)  : Színes LCD
Profile Description ML (cs-CZ)  : Barevný LCD
Profile Description ML (da-DK)  : LCD-farveskærm
Profile Description ML (nl-NL)  : Kleuren-LCD
Profile Description ML (fi-FI)  : Väri-LCD
Profile Description ML (it-IT)  : LCD colori
Profile Description ML (es-ES)  : LCD color
Profile Description ML (ro-RO)  : LCD color
Profile Description ML (fr-CA)  : ACL couleur
Profile Description ML (uk-UA)  : Кольоровий LCD
Profile Description ML (he-IL)  : LCD צבעוני
Profile Description ML (zh-TW)  : 彩色LCD
Profile Description ML (vi-VN)  : LCD Màu
Profile Description ML (sk-SK)  : Farebný LCD
Profile Description ML (zh-CN)  : 彩色LCD
Profile Description ML (ru-RU)  : Цветной ЖК-дисплей
Profile Description ML (en-GB)  : Colour LCD
Profile Description ML (fr-FR)  : LCD couleur
Profile Description ML (hi-IN)  : रगन LCD
Profile Description ML (th-TH)  : LCD ส
Profile Description ML (ca-ES)  : LCD en color
Profile Description ML (en-AU)  : Colour LCD
Profile Description ML (es-XL)  : LCD color
Profile Description ML (de-DE)  : Farb-LCD
Profile Description ML          : Color LCD
Profile Description ML (pt-BR)  : LCD Colorido
Profile Description ML (pl-PL)  : Kolor LCD
Profile Description ML (el-GR)  : Έγχρωμη οθόνη LCD
Profile Description ML (sv-SE)  : Färg-LCD
Profile Description ML (tr-TR)  : Renkli LCD
Profile Description ML (pt-PT)  : LCD a Cores
Profile Description ML (ja-JP)  : カラーLCD
Profile Copyright               : Copyright Apple Inc., 2020
Media White Point               : 0.94955 1 1.08902
Red Matrix Column               : 0.51099 0.23955 -0.00104
Green Matrix Column             : 0.29517 0.69981 0.04224
Blue Matrix Column              : 0.15805 0.06064 0.78369
Red Tone Reproduction Curve     : (Binary data 2060 bytes, use -b option to extract)
Video Card Gamma                : (Binary data 48 bytes, use -b option to extract)
Native Display Info             : (Binary data 62 bytes, use -b option to extract)
Chromatic Adaptation            : 1.04861 0.02332 -0.05034 0.03018 0.99002 -0.01714 -0.00922 0.01503 0.75172
Make And Model                  : (Binary data 40 bytes, use -b option to extract)
Blue Tone Reproduction Curve    : (Binary data 2060 bytes, use -b option to extract)
Green Tone Reproduction Curve   : (Binary data 2060 bytes, use -b option to extract)
Exif Byte Order                 : Big-endian (Motorola, MM)
X Resolution                    : 144
Y Resolution                    : 144
Resolution Unit                 : inches
User Comment                    : Screenshot
Exif Image Width                : 594
Exif Image Height               : 1104
Pixels Per Unit X               : 5669
Pixels Per Unit Y               : 5669
Pixel Units                     : meters
XMP Toolkit                     : XMP Core 5.4.0
Apple Data Offsets              : (Binary data 28 bytes, use -b option to extract)
Warning                         : [minor] Trailer data after PNG IEND chunk
Image Size                      : 594x1104
Megapixels                      : 0.656
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ strings dolls.jpg                                                                
IHDR
eiCCPICC Profile
 *!     $
(VtUD
@Z(O
eMHKg
aPn;
b1d#9t
}>?g
 _98
2\-h
r.G;
"IJ,d]
},#[
`,BQX
X@      k
I5O7
Nh?B
pfo(
8}=R
.
.
.
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ binwalk dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg
651600        0x9F150         End of Zip archive, footer length: 22

                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ binwalk -e dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg
651600        0x9F150         End of Zip archive, footer length: 22

                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ ls
capture.pcap  dolls.jpg  _dolls.jpg.extracted  picopico.key
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ cd _dolls.jpg.extracted 
                                                                                       
┌──(kali㉿kali)-[~/Descargas/Forensic/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images
                                                                                       
┌──(kali㉿kali)-[~/Descargas/Forensic/_dolls.jpg.extracted]
└─$ cd base_images         
                                                                                       
┌──(kali㉿kali)-[~/Descargas/Forensic/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg
                                                                                       
┌──(kali㉿kali)-[~/Descargas/Forensic/_dolls.jpg.extracted/base_images]
└─$ open 2_c.jpg  
                                                                                       
┌──(kali㉿kali)-[~/Descargas/Forensic/_dolls.jpg.extracted/base_images]
└─$ binwalk -e 2_c.jpg     
c
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
d0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196042, uncompressed size: 201444, name: base_images/3_c.jpg
383804        0x5DB3C         End of Zip archive, footer length: 22
383915        0x5DBAB         End of Zip archive, footer length: 22

                                                                                       
┌──(kali㉿kali)-[~/Descargas/Forensic/_dolls.jpg.extracted/base_images]
└─$ cd _2_c.jpg.extracted/base_images
                                                                                       
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg
                                                                                       
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ open 3_c.jpg 
                                                                                       
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk -e 3_c.jpg               

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77650, uncompressed size: 79806, name: base_images/4_c.jpg
201422        0x312CE         End of Zip archive, footer length: 22

                                                                                       
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd _3_c.jpg.extracted            
                                                                                       
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ ls
1E2D6.zip  base_images
                                                                                       
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ cd _3_c.jpg.extracted/base_images
cd: no existe el fichero o el directorio: _3_c.jpg.extracted/base_images
                                                                                       
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ cd base_images                   
                                                                                       
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg
                                                                                       
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk -e 4_c.jpg               

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 62, uncompressed size: 81, name: flag.txt
79784         0x137A8         End of Zip archive, footer length: 22

                                                                                       
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ strings 4_c.jpg        
IHDR
eiCCPICC Profile
 *!     $
(VtUD
@Z(O
eMHKg
aPn;
b1d#9t
}>?g
 _98
2\-h
r.G;
"IJ,d]
},#[
R2RjS
/kCV
+X+x&
E+EO
B#xx
3\f,
+*+>,
5rkC
f;*v|
+aW[
-86p
Uk_|
d|9_}
Cx;0
eXIfMM
ASCII
Screenshot
        pHYs
iTXtXML:com.adobe.xmp
<x:xmpmeta xmlns:x="adobe:ns:meta/" x:xmptk="XMP Core 5.4.0">
   <rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
      <rdf:Description rdf:about=""
            xmlns:exif="http://ns.adobe.com/exif/1.0/">
         <exif:PixelXDimension>320</exif:PixelXDimension>
         <exif:UserComment>Screenshot</exif:UserComment>
         <exif:PixelYDimension>768</exif:PixelYDimension>
      </rdf:Description>
   </rdf:RDF>
</x:xmpmeta>
iDOT
IDATx
uUY?p^5
PD0@DA
MC!ADq
;v`^
'T0J
2zaH
+_Ya'8
bbv|
Bx`&|
|`|sV}
}s|o|
KzR>a
0@/~
r a3
?Zc1
sBUO]
IEND
flag.txtUT
O`ux
flag.txtUT
O`ux
                                                                                       
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted            
                                                                                       
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                                       
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt         
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}                                                                                       
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ 
                                                                                       
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ 


```


## Bandera 
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32} 


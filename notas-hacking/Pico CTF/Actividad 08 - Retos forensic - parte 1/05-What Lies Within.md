# What Lies Within




## Descripción
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

## Pistas
- There is data encoded somewhere... there might be an online decoder.

## Solución

- El reto nos da un archivo .png en el cual contiene la bandera
- Se puede resolver de 2 formas:

1.- Solución:
	- Entrar a  [steganography online](https://stylesuxx.github.io/steganography/), cargamos la imagen, damos click en decode 
	- Se obtine la bandera 

2.- Solución:
``` bash
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ ls
buildings.png  capture.pcap  flag.png  garden.jpg  pico_img.png
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ file buildings.png 
buildings.png: PNG image data, 657 x 438, 8-bit/color RGBA, non-interlaced
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ open buildings.png 
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ zsteg -a buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
^C/var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:56:in `shift': Interrupt
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:56:in `block (3 levels) in color_extract'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:56:in `times'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:56:in `block (2 levels) in color_extract'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:128:in `block (2 levels) in coord_iterator'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:128:in `step'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:128:in `block in coord_iterator'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:128:in `step'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:128:in `coord_iterator'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:41:in `block in color_extract'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:40:in `catch'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor/color_extractor.rb:40:in `color_extract'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/extractor.rb:23:in `extract'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:265:in `check_channels'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:192:in `check_channels'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:109:in `block (5 levels) in check'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:109:in `each'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:109:in `block (4 levels) in check'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:101:in `each'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:101:in `block (3 levels) in check'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:99:in `each'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:99:in `block (2 levels) in check'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:98:in `each'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:98:in `block in check'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:97:in `each'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/checker.rb:97:in `check'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/cli/cli.rb:258:in `check'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/cli/cli.rb:172:in `block (2 levels) in run'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/cli/cli.rb:168:in `each'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/cli/cli.rb:168:in `block in run'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/cli/cli.rb:161:in `each'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/cli/cli.rb:161:in `each_with_index'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg/cli/cli.rb:161:in `run'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/lib/zsteg.rb:26:in `run'
 from /var/lib/gems/3.0.0/gems/zsteg-0.2.13/bin/zsteg:8:in `<top (required)>'
 from /usr/local/bin/zsteg:25:in `load'
 from /usr/local/bin/zsteg:25:in `<main>'
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ 

```


## Bandera
picoCTF{h1d1ng_1n_th3_b1t5}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| zsteg| detectar datos ocultos en PNG|

## Referencias
- [steganography online](https://stylesuxx.github.io/steganography/)
- [zsteg](https://www.aldeid.com/wiki/Zsteg)

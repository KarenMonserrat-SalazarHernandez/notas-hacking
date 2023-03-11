# Tab, Tab, Attack


## Descripción
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip)

## Pistas
- After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...

## Solución

- El desafío nos da un archivo zip para descargar el cual descargamos y descomprimimos en ternimal:
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
 Addadshashanammu.zip                  
┌──(kali㉿kali)-[~/Descargas]
└─$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-hay
```

- Suponiendo que la bandera esta en el último directorio.
- Cambiamos de directorio de trabajo actual al último, terminamos con un archivo llamado "fang-of-haynekhtnamet". Al ejecutar el comando de archivo, vemos que es un archivo ejecutable ELF de 64 bits y lo ejecutamos usando "./" en la terminal de Linux para obtener la bandera:
```
┌──(kali㉿kali)-[~/Descargas]
└─$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ls
fang-of-haynekhtnamet
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}
└─$ 

```

## Bandera
picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}

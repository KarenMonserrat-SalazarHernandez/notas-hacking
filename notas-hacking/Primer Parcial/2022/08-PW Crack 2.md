# PW Crack 2



## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level2.flag.txt.enc) in the same directory too.

## Pistas
- Does that encoding look familiar?
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

- El desafío nos da dos archivos para descargar el cual dentro de esos dos  archivos tenemos que encontrar la contraseña para obtener la bandera:
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
 level2.flag.txt.enc   
 level2.py            
└─$ cat level2.py
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()
┌──(kali㉿kali)-[~/Descargas]
└─$ python3         
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39))
4ec9
>>> 
zsh: suspended  python3
┌──(kali㉿kali)-[~/Descargas]
└─$ python level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
┌──(kali㉿kali)-[~/Descargas]
└─$ 

```

- Con el comando cat podemos ver que es lo que contiene el archivo level2.py.
- Dentro del archivo level1.py hay  lineas de código donde se compara si la contraseña ingresada es la correcta en este caso "chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ".
- Del código obtenemos la contraseña para poder ingresar a obtener la bandera.
-  La contraseña para obtener la bandera contiene algunos caracteres ASCII. 
- Se convierten los caracteres usando python3.
-  Se imprime la cadena de la bandera para obtener la contraseña adecuada.
- Obtenemo la contraseña convertida "4ec9".
- Ejecutamos el archivo en python e ingresamos la contraseña.
- Y de esta manera obtenemos la bandera


## Bandera
picoCTF{tr45h_51ng1ng_9701e681}


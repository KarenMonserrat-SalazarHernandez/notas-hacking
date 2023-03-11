# PW Crack 3



## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/24/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/24/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/24/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Pistas
- To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
- To exit `bvi` type `:q` and press enter.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

- El desafío nos da tres archivos para descargar el cual dentro de esos tres  archivos tenemos que encontrar la contraseña para obtener la bandera:
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
 level3.flag.txt.enc   level3.py  
 level3.hash.bin  
┌──(kali㉿kali)-[~/Descargas]
└─$ cat level3.py
import hashlib

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

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]
┌──(kali㉿kali)-[~/Descargas]
└─$ python level3.py
Please enter correct password for flag: f09e
That password is incorrect
┌──(kali㉿kali)-[~/Descargas]
└─$ python level3.py
Please enter correct password for flag: 4dcf
That password is incorrect
┌──(kali㉿kali)-[~/Descargas]
└─$ python level3.py
Please enter correct password for flag: 87ab
That password is incorrect
└─$ python level3.py
Please enter correct password for flag: dba8
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}
┌──(kali㉿kali)-[~/Descargas]
└─$ 
```

- Con el comando cat podemos ver que es lo que contiene el archivo level2.py.
- Dentro del archivo level1.py hay  lineas de código donde se compara si la contraseña ingresada es la correcta en este caso nos da 7 posibles contraseñas, y solo una es la correcta.
-  Para obtener la contraseña de la bandera hay que ingresar una por una hasta encontrar la correcta.
- La contraseña correcta es "dba8", ofortunadamente no ingresamos todas las posibles contraseñas para dar con la buena.
- Obtenemo la contraseña convertida "dba8".
- Para cada posible contraseña tenemos que ejeutar el archivo en python e ingresamos la contraseña.
- Y de esta manera obtenemos la bandera


## Bandera
picoCTF{m45h_fl1ng1ng_cd6ed2eb}


# miniRSA




## Descripción
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext)? Something seems a bit small.

## Pistas
- RSA [tutorial](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
- How could having too small an e affect the security of this 2048 bit key?
- Make sure you don't lose precision, the numbers are pretty big (besides the e value)

## Solución

c = mensaje cifrado
m = mensaje en texto plano
p = primo 1
q = primo 2
n = modulo 
tn = totien n (euler)
e = exponente 2^16+1=65537
e , n = llave pública
d = llave privada

n  = p * q
tn = (p - 1) * (q - 1)
d = e modinv tn - inverse (e, tn)

Encriptar          : c = m ^ e mod n - pow(m, e, n)
Desencriptar    : m = c ^ d mod n - pow(c, d, n)

c = m ^ e mod n
c = m ^ 3
m = raiz3 c

``` bash
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ ls
ciphertext
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ cat ciphertext                                      

N: 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673
e: 3

ciphertext (c): 2205316413931134031074603746928247799030155221252519872650073010782049179856976080512716237308882294226369300412719995904064931819531456392957957122459640736424089744772221933500860936331459280832211445548332429338572369823704784625368933 
                                                                            
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ 

```

``` bash
>>> from gmpy2 import *
>>> from Crypto.Util.number import long_to_bytes
>>> gmpy2.get_context().precision=2048
>>> 
>>> e = 3
>>> c = 2205316413931134031074603746928247799030155221252519872650073010782049179856976080512716237308882294226369300412719995904064931819531456392957957122459640736424089744772221933500860936331459280832211445548332429338572369823704784625368933
>>> root, exact = iroot(c, e)
>>> root
mpz(13016382529449106065894479374027604750406953699090365388203708028670029596145277)
>>> print( long_to_bytes(root))
b'picoCTF{n33d_a_lArg3r_e_ccaa7776}'
>>> 
```

## Bandera 
picoCTF{n33d_a_lArg3r_e_ccaa7776}

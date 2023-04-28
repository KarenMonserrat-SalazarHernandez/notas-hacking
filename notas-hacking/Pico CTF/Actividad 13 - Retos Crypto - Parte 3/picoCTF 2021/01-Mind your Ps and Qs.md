# Mind your Ps and Qs



## Descripción
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values)

## Pistas
- Bits are expensive, I used only a little bit over 100 to save money

## Solución

RSA
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

- Contenido del archivo:
``` bash
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ ls
values
                                                                            
┌──(kali㉿kali)-[~/Descargas/Crypto]
└─$ cat values 
Decrypt my super sick RSA:
c: 964354128913912393938480857590969826308054462950561875638492039363373779803642185
n: 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
e: 65537  

```

- Con ayuda de [factordb](http://factordb.com/index.php?query=1584586296183412107468474423529992275940096154074798537916936609523894209759157543) factorizamos n:
``` bash
n: 1584586296183412107468474423529992275940096154074798537916936609523894209759157543

- 2434792384523484381583634042478415057961
- 650809615742055581459820253356987396346063
``` 

- Despues de factorizar n obtenemos los valores de p y q , y aplicamos las formulas :
``` bash
>>> c = 964354128913912393938480857590969826308054462950561875638492039363373779803642185
>>> n = 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
>>> p = 2434792384523484381583634042478415057961
>>> q = 650809615742055581459820253356987396346063
>>> e = 65537
>>> 
>>> tn = (p - 1) * (q - 1)
>>> d = inverse(e, tn)
>>> m = pow(c, d, n)
>>> m
13016382529449106065927291425342535437996222135352905256639684640304028661985917
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_73918962}'
>>> 

``` 

## Bandera 
picoCTF{sma11_N_n0_g0od_73918962}

## Referencias
- [factordb](http://factordb.com/index.php?query=1584586296183412107468474423529992275940096154074798537916936609523894209759157543)


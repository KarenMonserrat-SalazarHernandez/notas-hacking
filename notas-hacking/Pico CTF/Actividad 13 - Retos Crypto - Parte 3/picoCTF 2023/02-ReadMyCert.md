# ReadMyCert




## Descripción
How about we take you on an adventure on exploring certificate signing requestsTake a look at this CSR file [here](https://artifacts.picoctf.net/c/424/readmycert.csr).

## Pistas
- Download the certificate signing request and try to read it.


- El archivo encrypted.txt contiene lo siguiente:
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
readmycert.csr
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ cat readmycert.csr 
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF81YWVi
MGQ0Zn0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBAMCkf11rmV8rgqPvC2ZiPA6W+5RfOTwU6u3WpGvLA+2YFzocBPut
aATTxTPB+uaN2ZN3Z5J2CTFGmPzI4sUQfSqhZGuAqbfMyDDR8pRswmIYVJ6s0Apc
Toi7H8m3IShSbeE0pZUSIJpbK1a7V6lJqgwFMDI1qrgNhGgZaMA/l+d2J0vC3EYd
AijwSs8APcp6woWbFGYwdw5KaBsjn23oVz2G4h3/TmdB5g5e6Oq+kgi38NEpRDS0
ylXo9mUko3FqS4I6y9gOtDEI4uZaCJZuXHDmBpqZ04MfXbIVlHjF9NMOjDvXLonN
650oaANBm4bhBlgid0Fx48Z36tbtAVivZEcCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAHZx6h9r
G/SE7RCoX6ndk5BOJprRiHpxOqPLAWcDyKHfStln0/HcQZzIrRVRsmoHiOmch+md
PBA1b+M5aj+3BWtPR9jOY4vht+ZmHAKa0WfQxwb2dBxsRPKTTDea0wN2u8BHLlSM
PbWPNuz+TKySL41xfwFuM4VN/ywn58GTvdb7HXgwNZCGgo2N1WhRq/dBMiagXMah
yb6gX4erugCu61T5tyD80hgsNBjaqyIdy/whRfC/Pmn3QHmdkqB5ZCPezwb2OLm4
5RDGv3WOB5q0BofoUGhVq757QE8qhL3oTvV2WlLoi3YWaZkJMCeR3vnH92cKC1Ov
FxdQuLOH8GMvl7U=
-----END CERTIFICATE REQUEST-----
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ 


```

- Con ayuda de la herramienta CSR de  [Decodificador de CSR](https://www.dondominio.com/es/products/ssl/tools/csr-decoder/) Decodificamos el contenido del archivo.
- Al decodificar obtenemos la bandera.

## Bandera
picoCTF{read_mycert_5aeb0d4f}


## Referencias
- [Decodificador de CSR](https://www.dondominio.com/es/products/ssl/tools/csr-decoder/) 
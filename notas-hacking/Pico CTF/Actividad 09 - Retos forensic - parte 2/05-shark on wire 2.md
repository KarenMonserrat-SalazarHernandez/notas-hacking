# shark on wire 2




## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Solución

- Se abre el archivo pcap con Wireshark.
- Se filtran los protocolos UDP
- Se observan los flujos y se busca en el contenido de los paquetes como  en "shark on wire 1" 
- Se observa un patron del paquete 32 al 60, ahí podria estar la bandera
- En los UDP streams podemos observar que el puerto origen comienza en 5000 en el puerto 22
- A partir del patron podemos decodificar para encontrar la bandera:
``` bash
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ ls
capture1.pcap
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ file capture1.pcap                         
capture1.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
                                                                                                                                                             
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ whireshark capture1.pcap &
[1] 113737  
                                                                                                                                                     

```

-  Decodificación en Nano para obtener la bandera:
```bash
from scapy.all import *

packets = rdpcap('capture1.pcap')

flag = ''

for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)
print(flag)

```

- 
```bash
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ python3 bandera.py                                                                          
picoCTF{p1LLf3r3d_data_v1a_st3g0}
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ 
```

## Bandera
picoCTF{p1LLf3r3d_data_v1a_st3g0}


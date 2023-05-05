# Packets Primer



## Descripción
Download the packet capture file and use packet analysis software to find the flag.

-   [Download packet capture](https://artifacts.picoctf.net/c/194/network-dump.flag.pcap)

## Pistas
- Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product.

## Solución

- Inspeccionamos `Follow TCP stream`, que revela la bandera, manualmente hay que quitar los espacios que hay en cada caracter de la bandera:
![[Pasted image 20230420191939.png]]

## Bandera
picoCTF{p4ck37_5h4rk_ceccaa7f}




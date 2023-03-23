# shark on wire 1



## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Pistas
- Try using a tool like Wireshark
- What are streams?

## Solución

WireShark es una herramienta que analiza los datos de la red a partir de una captura. Las pistas nos dice que analicemos los streams. Una vez que abrimos la captura de paquetes en WireShark, podemos comenzar filtrando los flujos.
- Filtramos las transmisiones UDP, comenzando con el filtro `udp.stream eq 0`en la barra de filtros de visualización.
- Se analiza esta transmisión yendo a Analizar > Seguir > Transmisión UDP . Esto nos dará algunos datos aleatorios, así que pasamos al siguiente filtro `udp.stream eq 1`. 
- Eventualmente en `udp.stream eq 6` encontramos la bandera.

## Bandera
picoCTF{StaT31355_636f6e6e}

## Referencias
- [WireShark](https://cso.computerworld.es/tendencias/que-es-wireshark-asi-funciona-la-nueva-tendencia-esencial-en-seguridad)




# Bandit Level 14 → Level 15


## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## Datos de acceso al nivel 
- bandit14
- fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Solución
``` bash
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

^C
bandit14@bandit:~$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| nc |  permite acceder a puertos TCP o UDP de la propia máquina o de otras máquinas remotas. También permite quedar a la escucha en un puerto dado (TCP o UDP) de la máquina local. |


## Referencias
- [Uso básico de servicios cliente-servidor](https://ccia.esei.uvigo.es/docencia/SCS/1011/practicas/practica-1/index.html#:~:text=netcat(nc)%20es%20un%20comando,UDP)

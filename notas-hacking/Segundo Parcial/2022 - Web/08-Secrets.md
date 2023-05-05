# Secrets




## Descripción
We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:52025/).

## Pistas
- folders folders folders

## Solución

- Inspeccionando el código fuente de la página  se encuentra una pista **secret/** y accedemos a ese directorio obteniendo lo siguiente:
![[Pasted image 20230421223828.png]]

- En **/secret** se  encontra otra página con un gif. Después se  Inspeccionando el código fuente de la página y  se encuentra una pista **hidden/** y accedemos a ese directorio y obtenemos el siguiente resultado:
![[Pasted image 20230421223932.png]]

- Nuevamente se  Inspeccionando el código fuente de la página y  se encuentra una pista **superhidden/** y accedemos a ese directorio y obtenemos el siguiente resultado:
![[Pasted image 20230421224134.png]]

- Finalmente se  Inspeccionando el código fuente de la página y  se encuentra la bandera:
![[Pasted image 20230421224159.png]]

## Bandera
picoCTF{succ3ss_@h3n1c@10n_39849bcf}


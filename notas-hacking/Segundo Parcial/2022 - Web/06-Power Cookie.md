# Power Cookie




## Descripción
Can you get the flag?Go to this [website](http://saturn.picoctf.net:57688/) and see what you can discover.

## Pistas
- Do you know how to modify cookies?

## Solución

- Se intenta acceder a la pagina web para encontrar la bandera:
![[Pasted image 20230421214930.png]]

- No se obtiene la bandera ya que no somos administradores:
![[Pasted image 20230421214951.png]]

- Se inspecciona la página web para cambiar el valor de las cookies  a 1 para que sea verdadero y poder encontrar la bandera:
![[Pasted image 20230421215236.png]]

- Una vez que se cambio el valor de la cookie se refresca la página para obtener la bandera:
![[Pasted image 20230421215258.png]]

## Bandera
picoCTF{gr4d3_A_c00k13_0d351e23}


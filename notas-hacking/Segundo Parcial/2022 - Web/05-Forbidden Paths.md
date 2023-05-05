# Forbidden Paths




## Descripción
Can you get the flag?Here's the [website](http://saturn.picoctf.net:52278/).We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

## Solución

- Se intenta ingresar con la información que nos da la informacion de la descripción del reto:
![[Pasted image 20230420211910.png]]

- No tenemos acceso con la información ingresada:
![[Pasted image 20230420211933.png]]

- Se hace otro intento de ingreso:
![[Pasted image 20230420212652.png]]

- Nuevamente no tenemos acceso:
![[Pasted image 20230420211933.png]]

- Como sabemos que estamos en `/usr/share/nginx/html/`, y queremos acceder a `/flag.txt`, podemos usar la ruta `../../../../flag.txt`para leer la bandera.
![[Pasted image 20230420212816.png]]

- Se obtiene la bandera:
![[Pasted image 20230420212747.png]]

## Bandera
picoCTF{7h3_p47h_70_5ucc355_6db46514}

## Notas adicionales
| Instrucción | Descripción |
|------ | -------------- |
| ./ | directorio actual |
| ../ | directorio adjunto |

## Referencias
- [Rutas de Archivos](https://ctftime.org/writeup/32842)


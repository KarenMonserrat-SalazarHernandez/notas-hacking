# Tapping




## Descripción
Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 21610`.

## Pistas
- What kind of encoding uses dashes and dots?
- The flag is in the format PICOCTF{}

## Solución

- Nos conectamos al puerto y obtenemos lo siguiente:
``` bash
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 21610
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ...-- ----. ----- ..--- ----- .---- ----. ..... .---- ----. } 
                                                                                                                                                            
┌──(kali㉿kali)-[~]
└─$ 
```

- Con ayuda de  [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Morse_Code('Space','Line%20feed')&input=Li0tLiAuLiAtLi0uIC0tLSAtLi0uIC0gLi4tLiB7IC0tIC0tLS0tIC4tLiAuLi4gLi4uLS0gLS4tLiAtLS0tLSAtLi4gLi4uLS0gLi0tLS0gLi4uIC4uLS4gLi4tIC0uIC4uLi0tIC0tLS0uIC0tLS0tIC4uLS0tIC0tLS0tIC4tLS0tIC0tLS0uIC4uLi4uIC4tLS0tIC0tLS0uIH0g) encontramos la Bandera al aplicar 
![[Pasted image 20230420014807.png]]

## Bandera 
picoCTF{M0RS3C0D31SFUN3902019519}

## Referencias
-   [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Morse_Code('Space','Line%20feed')&input=Li0tLiAuLiAtLi0uIC0tLSAtLi0uIC0gLi4tLiB7IC0tIC0tLS0tIC4tLiAuLi4gLi4uLS0gLS4tLiAtLS0tLSAtLi4gLi4uLS0gLi0tLS0gLi4uIC4uLS4gLi4tIC0uIC4uLi0tIC0tLS0uIC0tLS0tIC4uLS0tIC0tLS0tIC4tLS0tIC0tLS0uIC4uLi4uIC4tLS0tIC0tLS0uIH0g)



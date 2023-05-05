#  Redaction gone wrong




## Descripción
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

## Pistas
- How can you be sure of the redaction?

## Solución

- Como no se puede ver todo el texto en formato PDF se convierte a texto con ayuda de la herrameinta [pdf2go](https://www.pdf2go.com/es/result#j=c7cbe598-6a2a-45e9-85dd-bb195178630a), al convertirlo podemos ver el texto completo donde se encuentra la bandera:

![[Pasted image 20230420193849.png]]

![[Pasted image 20230420193921.png]]

## Bandera
picoCTF{C4n_Y0u_S33_m3_fully}

## Referencias
- [pdf2go](https://www.pdf2go.com/es/result#j=c7cbe598-6a2a-45e9-85dd-bb195178630a)




# Wireshark doo dooo do doo...




## Descripción
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/ae5b2bc07928fca272ff3900dc9a6cef/shark1.pcapng).

## Solución

- Al entrar a Wireshark e inspeccionar en secuencia HTTP nos encontramos una serie de caracteres que se asemeja a la bandera:
![[Pasted image 20230420181133.png]]

Con ayuda de [CyberChef](https://gchq.github.io/CyberChef/) aplicamos rot13 para encontrar la bandera:
![[Pasted image 20230420181636.png]]

## Bandera
picoCTF{p33kab00_1_s33_u_deadbeef}

## Referencias
- [CyberChef](https://gchq.github.io/CyberChef/) 



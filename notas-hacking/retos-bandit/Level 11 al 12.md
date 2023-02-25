# Bandit Level 11 → Level 12


## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

## Datos de acceso al nivel 
- bandit11
- 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solución
``` bash
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| tr | nos permite traducir o eliminar caracteres |

| Concepto | Descripción |
|------ | -------------- |
| ROT13 | "rotar por 13 lugares",  es un [cifrado de sustitución](https://en.wikipedia.org/wiki/Substitution_cipher "cifrado de sustitución") de letra simple que reemplaza una letra con la letra 13 después de ella en el alfabeto. |"

## Referencias
- [ROT13](https://en.wikipedia.org/wiki/ROT13)
-  [Writeup - Wargame Bandit - Parte 2](https://www.w0lff4ng.org/wargame-bandit-2/)

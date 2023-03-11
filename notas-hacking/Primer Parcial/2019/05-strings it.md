# strings it


## Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) without running it?

## Pistas
- [strings](https://linux.die.net/man/1/strings)

## Solución
``` bash
kmonshe-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_827aee91}
kmonshe-picoctf@webshell:~$ 
```

## Bandera
picoCTF{5tRIng5_1T_827aee91}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| strings |  imprime las cadenas de caracteres imprimibles en los archivos |
| grep | usada para buscar cadenas de texto y encontrar coincidencias dentro de este |

## Referencias
- [strings](https://linux.die.net/man/1/strings)
- [grep](https://keepcoding.io/blog/que-es-el-comando-grep-y-como-usarlo-en-linux/#:~:text=As%C3%AD%20pues%2C%20Grep%20(por%20sus,palabras%20dentro%20de%20un%20fichero.)


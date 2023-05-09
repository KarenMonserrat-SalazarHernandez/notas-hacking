# reverse_cipher - picoCTF 





## Descripción
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this). Can you reverse the flag.

## Pistas
- objdump and Gihdra are some tools that could assist with this

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ ls
rev  rev_this
                                                                            
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ file rev     
rev: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=523d51973c11197605c76f84d4afb0fe9e59338c, not stripped
                                                                            
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ file rev_this 
rev_this: ASCII text, with no line terminators
                                                                            
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ cat rev_this
picoCTF{w1{1wq85jc=2i0<}                                                                            
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ 


``` 

``` bash
void main(void)

{
  size_t sVar1;
  char local_58 [23];
  char local_41;
  int local_2c;
  FILE *local_28;
  FILE *flagfile;
  uint local_14;
  int local_10;
  char local_9;
  
  flagfile = fopen("flag.txt","r");
  local_28 = fopen("rev_this","a");
  if (flagfile == (FILE *)0x0) {
    puts("No flag found, please make sure this is run on the server");
  }
  if (local_28 == (FILE *)0x0) {
    puts("please run this on the server");
  }
  sVar1 = fread(local_58,0x18,1,flagfile);
  local_2c = (int)sVar1;
  if ((int)sVar1 < 1) {
                    /* WARNING: Subroutine does not return */
    exit(0);
  }
  for (local_10 = 0; local_10 < 8; local_10 = local_10 + 1) {
    local_9 = local_58[local_10];
    fputc((int)local_9,local_28);
  }
  for (local_14 = 8; (int)local_14 < 0x17; local_14 = local_14 + 1) {
    if ((local_14 & 1) == 0) {
      local_9 = local_58[(int)local_14] + '\x05';
    }
    else {
      local_9 = local_58[(int)local_14] + -2;
    }
    fputc((int)local_9,local_28);
  }
  local_9 = local_41;
  fputc((int)local_41,local_28);
  fclose(local_28);
  fclose(flagfile);
  return;
}


``` 


``` bash
rev = open('rev_this').read()


for j in range(8,len(rev)-1):

        if j & 1 == 0:
                print(chr(ord(rev[j])-5),end='')

        else:
                print(chr(ord(rev[j])+2),end='')


``` 

``` bash  
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ cat rev_this 
picoCTF{w1{1wq85jc=2i0<}                                                                            
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ python3 flag.py
r3v3rs37ee84d27                                                                            
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ 


``` 

## Bandera 
picoCTF{r3v3rs37ee84d27}







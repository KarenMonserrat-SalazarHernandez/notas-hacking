# Bandit Level 22 → Level 23


## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

## Datos de acceso al nivel 
- bandit22
- WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

## Solución
``` bash
bandit22@bandit:~$  ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit22@bandit:~$  cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$  cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ whoami
bandit22
bandit22@bandit:~$ myname=bandit23
bandit22@bandit:~$ echo $(echo I am user $myname | md5sum | cut -d ' ' -f 1)
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$  cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
bandit22@bandit:~$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| whoami | es un comando simple, utilizado para imprimir el nombre de usuario efectivo del usuario actual cuando se invoca|
| cut -d ' ' -f1 | separa el mensaje MD5 usando el delimitador de un espacio `' '`, y muestra el primer campo de esto |

## Referencias
- [Comando whoami](http://codigoelectronica.com/blog/comando-whoami#:~:text=Whoami%20(%C2%BFWho%20am%20I%3F,usuario%20actual%20cuando%20se%20invoca.)
- [Overthewire: Bandit - Niveles 20 al 32](https://www.w0lff4ng.org/wargame-bandit-3/)

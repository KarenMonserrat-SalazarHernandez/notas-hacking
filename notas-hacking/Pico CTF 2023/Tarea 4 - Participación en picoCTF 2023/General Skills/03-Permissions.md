# Permissions




## Descripción
Can you read files in the root file? The system admin has provisioned an account for you on the main server: `ssh -p 50040 picoplayer@saturn.picoctf.net` 
Password: `pEN9KN1qYm` 
Can you login and read the root file?

## Pistas
- What permissions do you have?

## Solución
``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ ssh -p 50040 picoplayer@saturn.picoctf.net  
The authenticity of host '[saturn.picoctf.net]:50040 ([13.59.203.175]:50040)' can't be established.
ED25519 key fingerprint is SHA256:Km7la74G7/fztU37KiXuMDlWhxowKKAxA3TjvWy1Y0o.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:50040' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 5.15.0-1031-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

picoplayer@challenge:~$ ls
picoplayer@challenge:~$ cd ..
picoplayer@challenge:/home$ ls
picoplayer
picoplayer@challenge:/home$ cd picoplayer/
picoplayer@challenge:~$ ls
picoplayer@challenge:~$ cd ..
picoplayer@challenge:/home$ cd ..
picoplayer@challenge:/$ cd ..
picoplayer@challenge:/$ ls
bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
picoplayer@challenge:/$ cd bin
picoplayer@challenge:/bin$ ls
'['                                   domainname                lslogins              rm                               tail
 addpart                              dpkg                      lsmem                 rmdir                            tar
 apt                                  dpkg-deb                  lsns                  rsh                              taskset
 apt-cache                            dpkg-divert               lzcat                 run-mailcap                      tee
 apt-cdrom                            dpkg-maintscript-helper   lzcmp                 run-parts                        tempfile
 apt-config                           dpkg-query                lzdiff                runcon                           test
 apt-get                              dpkg-split                lzegrep               rview                            tic
 apt-key                              dpkg-statoverride         lzfgrep               rvim                             timedatectl
 apt-mark                             dpkg-trigger              lzgrep                savelog                          timeout
 arch                                 du                        lzless                scp                              tload
 awk                                  echo                      lzma                  script                           toe
 b2sum                                edit                      lzmainfo              scriptreplay                     top
 base32                               editor                    lzmore                sdiff                            touch
 base64                               egrep                     man                   sed                              tput
 basename                             env                       mawk                  see                              tr
 bash                                 ex                        mcookie               select-editor                    true
 bashbug                              expand                    md5sum                sensible-browser                 truncate
 bootctl                              expiry                    md5sum.textutils      sensible-editor                  tset
 bunzip2                              expr                      mesg                  sensible-pager                   tsort
 busctl                               factor                    mkdir                 seq                              tty
 bzcat                                faillog                   mkfifo                setarch                          tzselect
 bzcmp                                fallocate                 mknod                 setpriv                          ucf
 bzdiff                               false                     mktemp                setsid                           ucfq
 bzegrep                              fgrep                     more                  setterm                          ucfr
 bzexe                                file                      mount                 sftp                             umount
 bzfgrep                              fincore                   mountpoint            sg                               uname
 bzgrep                               find                      mv                    sh                               uncompress
 bzip2                                findmnt                   namei                 sha1sum                          unexpand
 bzip2recover                         flock                     nawk                  sha224sum                        uniq
 bzless                               fmt                       networkctl            sha256sum                        unlink
 bzmore                               fold                      networkd-dispatcher   sha384sum                        unlzma
 c_rehash                             free                      newgrp                sha512sum                        unshare
 captoinfo                            getconf                   nice                  shred                            unxz
 cat                                  getent                    nisdomainname         shuf                             update-alternatives
 catchsegv                            getopt                    nl                    skill                            update-mime-database
 cautious-launcher                    gpasswd                   nohup                 slabtop                          uptime
 chage                                gpgv                      nproc                 sleep                            users
 chardet3                             grep                      nsenter               slogin                           utmpdump
 chardetect3                          groups                    numfmt                snice                            vdir
 chattr                               gunzip                    od                    sort                             vi
 chcon                                gzexe                     openssl               split                            view
 chfn                                 gzip                      pager                 ssh                              vim
 chgrp                                head                      partx                 ssh-add                          vim.basic
 chmod                                helpztags                 passwd                ssh-agent                        vimdiff
 choom                                hostid                    paste                 ssh-argv0                        vimtutor
 chown                                hostname                  pathchk               ssh-copy-id                      vmstat
 chrt                                 hostnamectl               pdb3                  ssh-import-id                    w
 chsh                                 i386                      pdb3.8                ssh-import-id-gh                 w.procps
 cksum                                iconv                     perl                  ssh-import-id-lp                 wall
 clear                                id                        perl5.30.0            ssh-keygen                       watch
 clear_console                        infocmp                   pgrep                 ssh-keyscan                      wc
 cmp                                  infotocap                 pidof                 stat                             wdctl
 comm                                 install                   pinky                 stdbuf                           wget
 compose                              ionice                    pkill                 stty                             whereis
 cp                                   ipcmk                     pldd                  su                               which
 csplit                               ipcrm                     pmap                  sudo                             who
 cut                                  ipcs                      pr                    sudoedit                         whoami
 cvtsudoers                           ischroot                  print                 sudoreplay                       x86_64
 dash                                 join                      printenv              sum                              xargs
 date                                 journalctl                printf                sync                             xauth
 dbus-cleanup-sockets                 kernel-install            prlimit               systemctl                        xdg-user-dir
 dbus-daemon                          kill                      ps                    systemd                          xdg-user-dirs-update
 dbus-monitor                         last                      ptx                   systemd-analyze                  xxd
 dbus-run-session                     lastb                     pwd                   systemd-ask-password             xz
 dbus-send                            lastlog                   pwdx                  systemd-cat                      xzcat
 dbus-update-activation-environment   lcf                       py3clean              systemd-cgls                     xzcmp
 dbus-uuidgen                         ldd                       py3compile            systemd-cgtop                    xzdiff
 dd                                   link                      py3versions           systemd-delta                    xzegrep
 deb-systemd-helper                   linux32                   pydoc3                systemd-detect-virt              xzfgrep
 deb-systemd-invoke                   linux64                   pydoc3.8              systemd-escape                   xzgrep
 debconf                              ln                        pygettext3            systemd-id128                    xzless
 debconf-apt-progress                 locale                    pygettext3.8          systemd-inhibit                  xzmore
 debconf-communicate                  locale-check              python3               systemd-machine-id-setup         yes
 debconf-copydb                       localectl                 python3.8             systemd-mount                    ypdomainname
 debconf-escape                       localedef                 rbash                 systemd-notify                   zcat
 debconf-set-selections               logger                    rcp                   systemd-path                     zcmp
 debconf-show                         login                     readlink              systemd-resolve                  zdiff
 delpart                              loginctl                  realpath              systemd-run                      zdump
 df                                   logname                   rename.ul             systemd-socket-activate          zegrep
 diff                                 ls                        renice                systemd-stdio-bridge             zfgrep
 diff3                                lsattr                    reset                 systemd-sysusers                 zforce
 dir                                  lsb_release               resizepart            systemd-tmpfiles                 zgrep
 dircolors                            lsblk                     resolvectl            systemd-tty-ask-password-agent   zless
 dirname                              lscpu                     rev                   systemd-umount                   zmore
 dmesg                                lsipc                     rgrep                 tabs                             znew
 dnsdomainname                        lslocks                   rlogin                tac
picoplayer@challenge:/bin$ cd ..
picoplayer@challenge:/$ cd ^C
picoplayer@challenge:/$ cd challenge/
picoplayer@challenge:/challenge$ ls
metadata.json
picoplayer@challenge:/challenge$ cat metadata.json 
{"flag": "picoCTF{uS1ng_v1m_3dit0r_55878b51}", "username": "picoplayer", "password": "pEN9KN1qYm"}
picoplayer@challenge:/challenge$ 
```

## Bandera
picoCTF{uS1ng_v1m_3dit0r_55878b51}
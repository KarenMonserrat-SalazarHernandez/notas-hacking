# Bandit Level 30 → Level 31


## Objetivo
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel 
- bandit30
- xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Solución
``` bash
bandit30@bandit:~$ mkdir /tmp/passbandit31
bandit30@bandit:~$ cd /tmp/passbandit31
bandit30@bandit:/tmp/passbandit31$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/passbandit31$ cd repo/
bandit30@bandit:/tmp/passbandit31/repo$ ls
README.md
bandit30@bandit:/tmp/passbandit31/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/passbandit31/repo$ git log
commit cf552c166d78421e64ddf52f850e680075d216e1 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:13 2023 +0000

    initial commit of README.md
bandit30@bandit:/tmp/passbandit31/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
bandit30@bandit:/tmp/passbandit31/repo$ git show-ref
cf552c166d78421e64ddf52f850e680075d216e1 refs/heads/master
cf552c166d78421e64ddf52f850e680075d216e1 refs/remotes/origin/HEAD
cf552c166d78421e64ddf52f850e680075d216e1 refs/remotes/origin/master
831aac2e2341f009e40e46392a4f5dd318483019 refs/tags/secret
bandit30@bandit:/tmp/passbandit31/repo$ git show 831aac2e2341f009e40e46392a4f5dd318483019
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/passbandit31/repo$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| git show-ref | muestra las referencias disponibles en un repositorio local junto con los ID de confirmación asociados |


## Referencias
- [git show-ref](https://git-scm.com/docs/git-show-ref)
- 

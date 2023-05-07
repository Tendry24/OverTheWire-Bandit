# *Ovethewire* 

# **level0**:
*On se connecte au premier niveau avec l’utilisateur bandit0 et le mot de passe bandit0 :*
### ssh bandit0@bandit.labs.overthewire.org -p2220

# level1:
- ## ls, 
- cat readme
> ## NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

# level2:
- ls , 
### *Une autre solution serait d’utiliser ./- ; le point . est utilisé pour dénommer le dossier courant, ici*
- cat ./-

> ## rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

# level3:
- ls,
### *L’espace entre des mots est interprétée par notre shell – ici Bash – comme une séparation entre des arguments. Il exécute cat en lui passant les quatre arguments spaces, in, this, et filename, ce qui en pratique lui demande de concaténer les quatre fichiers spaces, in, this, et filename.*

### *Il existe divers moyens de forcer Bash à ne pas interpréter les espaces. Je peux soit passer le nom du fichier entre des guillemets, soit échapper chaque espace avec un antislash \ :*
- cat "spaces in this filename"

> ## aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

# level4:
- ls,
### *Ici, le fichier contenant le mot de passe est dans le dossier inhere. Cependant, ce dernier semble vide :*
- cd inhere,
### *En réalité il n’en est rien. En passant l’option -a à ls, je peux forcer l’affichage d’un fichier appelé .hidden :*
- ls -all,
- cat .hiden
> ## 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

 # level5:
- ls  , 
### *Dans le niveau 4, je retrouve un dossier inhere qui cette fois contient dix fichiers :*
- file inhere/* ,
### *La description du niveau m’indique que le mot de passe est contenu dans le seul fichier directement lisible. Je peux soit essayer de lire un à un tous les fichiers jusqu’à trouver le bon, soit en profiter pour vous introduire le programme file qui sert à déterminer le type d’un fichier en fonction de son contenu :*
- cat inhere/-file07
> ## lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

# level6:
### *Le programme find peut être utilisé pour fouiller récursivement une arborescence de fichiers. Moultes options sont possibles pour filtrer les résultats, et je me sers des fonctionnalités fournies par -size et -executable :*
- find ./inhere -type f -size 1033c ! -executable -exec file {} \; | grep "ASCII text",
### *Il se trouve qu’un seul fichier correspond à ces deux conditions, et je n’ai pas besoin d’ajouter une vérification pour la première caractéristique « lisible par un humain ». Ce filtre n’est en outre pas proposé directement par find.*
- cd inhere ,
- cd maybehere07,cat .file2
> ## P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

# level7:
- find / -user bandit7 -group bandit6 -size 33c 2>&1 | grep -F -v Permission | grep -F -v directory,
- cat /var/lib/dpkg/info/bandit7.password
> ## z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

# level8:
- cat data.txt | grep millionth
> ## TESKZC0XvTetK0S9xNwm25STk5iWrBvP

# level 9: 
- ls,
- cat data.txt | sort | uniq -c -u
> ## EN632PlfYiZbn3PhVK3XOGSlNInNE00t

# level10: 
- ls,
- strings data.txt | grep ====
> ## G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

# level11:
- ls
- cat data.txt,cat data.txt | base64 -d
> ## 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

# level12:
- ls
- cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
> ## JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## level13:
- ls,
- mkdir /tmp/tendry,
- cd /tmp/tendry,
- cp ~/data.txt .,
- ls,
- cat data.txt
 - xxd -r data.txt > data.gz
 - file data.gz
  - gzip -d data.gz
 - ls
 - file data
 - bzip2 -d data
 - ls
 - file data.out
 - mv data.out data4.gz
 - gzip -d data4.gz
 - ls
 - file data4
 - tar xvf data4
 - file data5.bin
 - tar xfv data5.bin
 - file data6.bin
 - bzip2 -d data6.bin
 - tar xfv data6.bin.out
 - file data8.bin
  - mv data8.bin data8.gz
 -  gzip -d data8.gz
 - file data8
- cat data8
   **The password is:** 
   > ##  wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

   ## level 14:
  - ls,
  - cat sshkey.private
 - ssh -i sshkey.private bandit14@localhost -p2220
 - cat /etc/bandit_pass/bandit14

  > ## fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

  ## level 15 : 
 - cat /etc/bandit_pass/bandit14
  >fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
 - netcat localhost 30000
   >fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
   Correct!
   > ## jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## level16 :
- cat /etc/bandit_pass/bandit15
>jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
> ## JQttfApK4SeyHwDlI9SXGR50qclOAil1
- openssl s_client -connect localhost:30001

## level 17:
- cat /etc/bandit_pass/bandit16
>JQttfApK4SeyHwDlI9SXGR50qclOAil1
- openssl s_client --connect localhost:31790
- mkdir /tmp/tendry2
- cd /tmp/tendry2
- touch private.key
- vim private.key
Once vim opens Press “i” to enter insert mode
Then use Ctrl + Shift + V to paste the copied key
>JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
Press “Esc” key to return to normal mode
Then type :wq to save and exit the file

*chmod 400 private.key*
*ls -l*
*ssh -i private.key*
*ssh -i private.key bandit17@localhost*
--Are you sure you want to continue connecting (yes/no/[fingerprint])? yes--


*cat /etc/bandit_pass/bandit17*

> ## VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

# level 18
- ls
- diff passwords.old passwords.new42c42
< glZreTEH1V3cGKL6g4conYqZqaEj0mte
---
 > ## hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

Note : When we try to login we are going to get kicked out saying “Byebye!”.
 This is normal, this is part of the challenge for the next level.


## level 19 :
ssh bandit18@bandit.labs.overthewire.org -p 2220 -t "/bin/sh"
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

- ls
- cat readme
- *awhqfNnAbc1naukrpqDYcF95h7HoMTrC*

## level 20 :
- ls
- ls -l
./bandit20-do 
> Run a command as another user.
  Example: ./bandit20-do id
- id
> uid=11019(bandit19) gid=11019(bandit19) groups=11019(bandit19)
- ./bandit20-do id
> uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
-  ./bandit20-do cat /etc/bandit_pass/bandit20
> ### VxCazJaVykI6W36BkBU0mJTCM8rR95XT

# level 21 :
- ssh bandit20@bandit.labs.overthewire.org -p 2220
>VxCazJaVykI6W36BkBU0mJTCM8rR95XT
- echo "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" | netcat -lp 1234 & 
> ### [1] 821982
- jobs
> [1]+  Running                 echo "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" | netcat -lp 1234 &
- ls
- ./suconnect 1234
>Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password :
### NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

# level 22 :
-  ls /etc/cron.d/
- cat /etc/cron.d/cronjob_bandit22
- cat /usr/bin/cronjob_bandit22.sh
>#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
- cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
> ### WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

# level 23 :
- ls /etc/cron.d/
- cat /etc/cron.d/cronjob_bandit23
-  cat /usr/bin/cronjob_bandit23.sh
- echo "I am user bandit23" | md5sum | cut -d ' ' -f 1
>8ca319486bfbbc3663ea0fbe81326349
- cat /tmp/8ca319486bfbbc3663ea0fbe81326349
> ### QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

# level 24 :
- ls /etc/cron.d/
- cat /etc/cron.d/cronjob_bandit24
- cat /usr/bin/cronjob_bandit24.sh
- mkdir /tmp/rand
- cd /tmp/rand
- ### Create a file called **script.sh** using vim or any other editor on the system and write the following code in the file.
- vim script.sh
- code to copy :
>#!/bin/bash 
---
 >cat /etc/bandit_pass/bandit24 > /tmp/rand/password
 - touch password
 - chmod 777 -R /tmp/rand



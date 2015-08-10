# gcb

github covert branch

Check out these URLs, then realise they can't be seen from Github navigation.
https://github.com/bawr/gcb/tree/f178662d86c110746147f1b7afe0ee9f5cda1a69
https://github.com/bawr/gcb/tree/9bc1b1643e491aa51035a51383af72e8d7eee0f9
https://github.com/bawr/gcb/tree/refs/remotes/origin/HEAD

```
alpine:~$ gcb-init bawr gcb gcb-secrets-hidden

Initialized empty Git repository in /home/bawr/gcb-secrets-hidden/.git/
Switched to a new branch 'master'
[master (root-commit) e6a0e13] initial covert commit

alpine:~$ cd gcb-secrets-hidden

alpine:~/gcb-secrets-hidden$ gcb-push

Counting objects: 2, done.
Writing objects: 100% (2/2), 178 bytes | 0 bytes/s, done.
Total 2 (delta 0), reused 0 (delta 0)
To https://github.com/bawr/gcb.git
 * [new branch]      HEAD -> origin/HEAD

alpine:~/gcb-secrets-hidden$ echo secret_one > top-secret.txt
alpine:~/gcb-secrets-hidden$ git add top-secret.txt
alpine:~/gcb-secrets-hidden$ git commit -m "Secret one"

[master f3b5817] Secret one
 1 file changed, 1 insertion(+)
 create mode 100644 top-secret.txt

alpine:~/gcb-secrets-hidden$ echo secret_two > top-secret.txt
alpine:~/gcb-secrets-hidden$ git add top-secret.txt
alpine:~/gcb-secrets-hidden$ git commit -m "Secret two"

[master f178662] Secret two
 1 file changed, 1 insertion(+), 1 deletion(-)

alpine:~/gcb-secrets-hidden$ gcb-push

Counting objects: 6, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (6/6), 501 bytes | 0 bytes/s, done.
Total 6 (delta 0), reused 0 (delta 0)
To https://github.com/bawr/gcb.git
   e6a0e13..f178662  HEAD -> origin/HEAD

alpine:~/gcb-secrets-hidden$ gcb-urls

tree: https://github.com/bawr/gcb/tree/f178662d86c110746147f1b7afe0ee9f5cda1a69
pack: https://github.com/bawr/gcb/archive/f178662d86c110746147f1b7afe0ee9f5cda1a69.zip

alpine:~/gcb-secrets$ ~/gcb/gcb-clear

To https://github.com/bawr/gcb.git
 - [deleted]         origin/HEAD

alpine:~/gcb-secrets-hidden$ git ls-remote

From https://github.com/bawr/gcb.git
8dbfeb09658f4dc780b065bdfe66543f2502b926        HEAD
8dbfeb09658f4dc780b065bdfe66543f2502b926        refs/heads/master
```

```
alpine:~$ gcb-init bawr gcb gcb-secrets-shown

Initialized empty Git repository in /home/bawr/gcb-secrets-shown/.git/
Switched to a new branch 'master'
[master (root-commit) 26f3656] initial covert commit

alpine:~$ cd gcb-secrets-shown/

alpine:~/gcb-secrets-shown$ echo top > top-covert.txt
alpine:~/gcb-secrets-shown$ git add top-covert.txt
alpine:~/gcb-secrets-shown$ git commit -m "Top covert"

[master 9bc1b16] Top covert
 1 file changed, 1 insertion(+)
 create mode 100644 top-covert.txt

alpine:~/gcb-secrets-shown$ ~/gcb/gcb-push

Counting objects: 5, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (5/5), 404 bytes | 0 bytes/s, done.
Total 5 (delta 0), reused 0 (delta 0)
To https://github.com/bawr/gcb.git
 * [new branch]      HEAD -> origin/HEAD

alpine:~/gcb-secrets-shown$ gcb-urls

tree: https://github.com/bawr/gcb/tree/9bc1b1643e491aa51035a51383af72e8d7eee0f9
pack: https://github.com/bawr/gcb/archive/9bc1b1643e491aa51035a51383af72e8d7eee0f9.zip

alpine:~/gcb-secrets-shown$ git ls-remote

From https://github.com/bawr/gcb.git
8dbfeb09658f4dc780b065bdfe66543f2502b926        HEAD
8dbfeb09658f4dc780b065bdfe66543f2502b926        refs/heads/master
9bc1b1643e491aa51035a51383af72e8d7eee0f9        refs/remotes/origin/HEAD
```

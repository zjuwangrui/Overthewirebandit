# level0 
ssh -p 2220 bandit0@bandit.labs.overthewire.org


# level0to1
## solution
ssh -p 2220 bandit1@bandit.labs.overthewire.org
6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR
## process
ls
cat readme

# level1to2
## solution
ssh -p 2220 bandit2@bandit.labs.overthewire.org
PK8fYLZg2hnHSz83plBL1iEPKdD3QToB
## process
bandit1@bandit:~$ cat ./-
PK8fYLZg2hnHSz83plBL1iEPKdD3QToB

# level2to3
## solution
ssh -p 2220 bandit3@bandit.labs.overthewire.org
7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME
## process
bandit2@bandit:~$ cat -- '--spaces in this filename--'
7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME

# level3to4
## solution
ssh -p 2220 bandit4@bandit.labs.overthewire.org
xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq
## process
bandit3@bandit:~$ ls -a
.  ..  .bash_logout  .bashrc  .profile  inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
bandit3@bandit:~/inhere$ cat '...Hiding-From-You'
xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq



# level4to5
## solution
ssh -p 2220 bandit5@bandit.labs.overthewire.org
6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG
## process
遍历来找
bandit4@bandit:~/inhere$ cat ./-file07
6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG

file来观察文件
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ file ./-file00
./-file00: data
bandit4@bandit:~/inhere$ file ./file07
./file07: cannot open `./file07' (No such file or directory)
bandit4@bandit:~/inhere$ file ./-file07
./-file07: ASCII text


# level5to6
## solution
ssh -p 2220 bandit6@bandit.labs.overthewire.org
pXa26xhMWaC2SvDotA4r9EgZkulOeSBW  
## process
bandit5@bandit:~/inhere$ find . -type f -size 1033c   # c表示字节
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
pXa26xhMWaC2SvDotA4r9EgZkulOeSBW


# level6to7
## solution
ssh -p 2220 bandit7@bandit.labs.overthewire.org
Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3
## process
bandit6@bandit:/home$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:/home$ cd /var/lib/dpkg/info/bandit7.password
-bash: cd: /var/lib/dpkg/info/bandit7.password: Not a directory
bandit6@bandit:/home$ cat /var/lib/dpkg/info/bandit7.password
Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3

# level7to8
## solution
ssh -p 2220 bandit8@bandit.labs.overthewire.org
VR1ljMayciFxbnUokuQmJFw6QC9VKtub
## process
bandit7@bandit:~$ grep millionth data.txt
millionth       VR1ljMayciFxbnUokuQmJFw6QC9VKtub

# level8to9
## solution
ssh -p 2220 bandit9@bandit.labs.overthewire.org
EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl
## process
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl

# level9to10
## solution
ssh -p 2220 bandit10@bandit.labs.overthewire.org
B0s2khmbT9u0geKuOoVGW3JZKhndE3BG
## process
bandit9@bandit:~$ strings -a data.txt | grep "^="
========== the
=zW}
========== password
=A@.
=l"C"m
========== B0s2khmbT9u0geKuOoVGW3JZKhndE3BG

# level10to11
## solution
ssh -p 2220 bandit11@bandit.labs.overthewire.org
pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro
## process
bandit10@bandit:~$ cat data.txt | base64 -d
The password is pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro

# level11to12
## solution
ssh -p 2220 bandit12@bandit.labs.overthewire.org
GROozWPO8QyN0mGrjUkID0WCYkZiQxrN
## process
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is GROozWPO8QyN0mGrjUkID0WCYkZiQxrN

# level12to13
## solution
ssh -p 2220 bandit13@bandit.labs.overthewire.org
qQYQiHOBPR8zR61qxYqX45quvihF2uzk
## process
bandit12@bandit:~$ mktemp -d
/tmp/tmp.H9bj0E7qLq
创建目录，通过file确认是什么文件压缩方法

# level13to14
## solution
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
## process
通过私钥登录
scp -P 2220 bandit13@bandit.labs.overthewire.org:~/sshkey.private ./
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
aaWecNkG4FhxJQxz07uiwzVP6bJiYS65 # password for bandit14

# level14to15
## solution
ssh -p 2220 bandit15@bandit.labs.overthewire.org
pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7
## process
bandit14@bandit:~$ nc localhost 30000
aaWecNkG4FhxJQxz07uiwzVP6bJiYS65
Correct!
pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7


# level15to16
## solution
ssh -p 2220 bandit16@bandit.labs.overthewire.org
kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V
## process
bandit15@bandit:~$ ncat --ssl localhost  30001
pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7
Correct!
kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V

# level16to17
## solution
ssh -i level16to17.key bandit17@bandit.labs.overthewire.org -p 2220
## process

bandit16@bandit:~$ nc -z localhost 31000-32000
Connection to localhost (127.0.0.1) 31046 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31518 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31691 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31790 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31960 port [tcp/*] succeeded!


bandit16@bandit:~$ ncat  localhost  31046
1
1
bandit16@bandit:~$ ncat  localhost  31691
1
1
bandit16@bandit:~$ ncat  localhost  31960
1
1
bandit16@bandit:~$ ncat --ssl localhost  31518
kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V
kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V

bandit16@bandit:~$ mktemp -d
/tmp/tmp.w2QZrXiKez
ncat --ssl localhost 31790 > /tmp/tmp.w2QZrXiKez/level16to17.key
scp -P 2220 bandit16@bandit.labs.overthewire.org:/tmp/tmp.w2QZrXiKez/level16to17.key ./

# level17to18
## solution
ssh -p 2220 bandit18@bandit.labs.overthewire.org
OQxXZjELndr90zuhOTDYBEomI0SZITXI
## process
bandit17@bandit:~$ diff -u passwords.new passwords.old
--- passwords.new       2026-06-24 14:58:52.323331835 +0000
+++ passwords.old       2026-06-24 14:58:52.315331770 +0000
@@ -39,7 +39,7 @@
 dCpvYCM0qdq9TrjpZj7YrflAUwF9GXvA
 6DtvOxp6oD5X4pmDv64fzsGHnwvpwP2m
 S1msSibMhCyxssqxe8a6dqIGcepeHwuu
-OQxXZjELndr90zuhOTDYBEomI0SZITXI
+qOg5pVOjPx9x9VccyYBADiT4xxyoUB8D
 M9PI7AAGrmH7gSFGnhXYDWFWXRbWZUqd
 DkEDNbP9brtv2ZcX0Ggk0ZnedqAYBuUd
 VNAHfTJr7rD8KwOJOS9loZRcYOt1QMu9


# level18to19
## solution
ssh -p 2220 bandit19@bandit.labs.overthewire.org
KpsOfPkcP7i1FlIExk2QEjyt6dw8dxZI
## process
ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"


# level19to20
## solution
ssh -p 2220 bandit20@bandit.labs.overthewire.org
4pIjcunZ0fK2vmp3IwfG8Vf7VhxD6pOA
## process
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
4pIjcunZ0fK2vmp3IwfG8Vf7VhxD6pOA

# level20to21
## solution
ssh -p 2220 bandit21@bandit.labs.overthewire.org
bW9kBv5WC3P4yoDyf12LSdGuNz5ka6hY
## process
bandit20@bandit:~$ echo "4pIjcunZ0fK2vmp3IwfG8Vf7VhxD6pOA" | nc -l -p 12345
bW9kBv5WC3P4yoDyf12LSdGuNz5ka6hY
bandit20@bandit:~$ ./suconnect 12345
Read: 4pIjcunZ0fK2vmp3IwfG8Vf7VhxD6pOA
Password matches, sending next password

# level21to22
## solution
ssh -p 2220 bandit22@bandit.labs.overthewire.org
RYVux2rHEm9tiXHmLFzuR7Vhx6AZQMEz
## process 
bandit21@bandit:~$ cd /etc/cron.d/
bandit21@bandit:/etc/cron.d$ ls
behemoth4_cleanup  clean_tmp  cronjob_bandit22  cronjob_bandit23  cronjob_bandit24  e2scrub_all  leviathan5_cleanup  manpage3_resetpw_job  otw-tmp-dir
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:/etc/cron.d$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
RYVux2rHEm9tiXHmLFzuR7Vhx6AZQMEz


# level21to22
## solution
ssh -p 2220 bandit22@bandit.labs.overthewire.org
RYVux2rHEm9tiXHmLFzuR7Vhx6AZQMEz
## process 
bandit21@bandit:~$ cd /etc/cron.d/
bandit21@bandit:/etc/cron.d$ ls
behemoth4_cleanup  clean_tmp  cronjob_bandit22  cronjob_bandit23  cronjob_bandit24  e2scrub_all  leviathan5_cleanup  manpage3_resetpw_job  otw-tmp-dir
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:/etc/cron.d$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
RYVux2rHEm9tiXHmLFzuR7Vhx6AZQMEz





# level22to23
## solution
ssh -p 2220 bandit23@bandit.labs.overthewire.org
gKXDTAXnIz3OBxiPjRZ2uqutUlPZrBsw
## process 
bandit22@bandit:~$ cd /etc/cron.d/
bandit22@bandit:/etc/cron.d$ ls
behemoth4_cleanup  clean_tmp  cronjob_bandit22  cronjob_bandit23  cronjob_bandit24  e2scrub_all  leviathan5_cleanup  manpage3_resetpw_job  otw-tmp-dir
bandit22@bandit:/etc/cron.d$ cat cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:/etc/cron.d$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:/etc/cron.d$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
gKXDTAXnIz3OBxiPjRZ2uqutUlPZrBsw

# level23to24
## solution
ssh -p 2220 bandit24@bandit.labs.overthewire.org
hVQMk3lJNsmQ7VF3ubyrNNBom7BOgVXv
## process
bandit23@bandit:/etc/cron.d$ mktemp -d
/tmp/tmp.ZW1ZuFNtdy

touch /tmp/tmp.ZW1ZuFNtdy/script.sh /create the script
nano /tmp/tmp.ZW1ZuFNtdy/script.sh /edit the script
chmod +x /tmp/tmp.ZW1ZuFNtdy/script.sh / qualify the script，权限会复制过去并且foo文件夹其实没有权限修改加chmod +x /var/spool/bandit24/foo/script.sh
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/bandit24_pass.txt
chmod 644 /tmp/bandit24_pass.txt
EOF

cp /tmp/tmp.ZW1ZuFNtdy/script.sh /var/spool/bandit24/foo/  /copy the script to the folder
cat /tmp/bandit24_pass.txt  /check the output
cat /var/spool/bandit24/foo/script.sh  /check the script
思路是把运行脚本得到答案。问题可能点：mktemp -d目录无权限。后来尝试加权限还是不行，应该不是因为这个；chmod 644也是有用的，不然读不了密码;chmod x没加倒是脚本无法被运行，应该是关键问题。

# level24to25
## solution
ssh -p 2220 bandit25@bandit.labs.overthewire.org
SoHfqMOEqIX2IYKVciZxvgpR9a2Djx4P
## process

bandit24@bandit:~$ mktemp -d
/tmp/tmp.9WqMYBQACK
touch /tmp/tmp.9WqMYBQACK/script.sh
nano /tmp/tmp.9WqMYBQACK/script.sh
#!/bin/bash
pass="hVQMk3lJNsmQ7VF3ubyrNNBom7BOgVXv"
for i in $(seq -w 0 9999); do
    echo "$pass $i"
done | nc localhost 30002

# level25to26
## solution
ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220
## process
scp -P 2220 bandit25@bandit.labs.overthewire.org:bandit26.sshkey ./


# level26to27
## solution
ssh -p 2220 bandit27@bandit.labs.overthewire.org
STJLJBRRphMxKB392CT4iOr5CbzPU9ER

## process
调查运行程序是more exit程序。调整window窗口大小触发more
输入v进入vim
:set shell=/bin/sh
:shell
ls
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
STJLJBRRphMxKB392CT4iOr5CbzPU9ER


# level27to28
## solution
ssh -p 2220 bandit28@bandit.labs.overthewire.org
y8Yd2ssKcpHpud7UvOSOxwamRMzIGIeQ
## process
git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo

# level28to29
## solution
ssh -p 2220 bandit29@bandit.labs.overthewire.org
xxxxxxxxxx
## process
git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo


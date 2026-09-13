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
ssh -i level16to17.key bandit14@bandit.labs.overthewire.org -p 2220
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
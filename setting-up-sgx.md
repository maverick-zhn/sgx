# Setting up SGX SDK on Ubuntu Linux 18.04 LTS
## Setting up SGX enabled Server

## Installing git
```
sudo apt-get update
sudo apt-get install git-core

git config --global user.name "Servio Palacios"
git config --global user.email "servio@palacios.com"

sudo apt-get install curl
```

## NVM
https://github.com/creationix/nvm

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash

spalacio@Qatar01:~/Desktop/repos/sgx$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 12819  100 12819    0     0   176k      0 --:--:-- --:--:-- --:--:--  176k
=> Downloading nvm from git to '/home/spalacio/.nvm'
=> Cloning into '/home/spalacio/.nvm'...
remote: Counting objects: 267, done.
remote: Compressing objects: 100% (242/242), done.
remote: Total 267 (delta 31), reused 86 (delta 15), pack-reused 0
Receiving objects: 100% (267/267), 119.46 KiB | 9.96 MiB/s, done.
Resolving deltas: 100% (31/31), done.
=> Compressing and cleaning up git repository

=> Appending nvm source string to /home/spalacio/.bashrc
=> Appending bash_completion source string to /home/spalacio/.bashrc
=> Close and reopen your terminal to start using nvm or run the following to use it now:

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

nvm install node

spalacio@Qatar01:~$ nvm install node
Downloading and installing node v10.1.0...
Downloading https://nodejs.org/dist/v10.1.0/node-v10.1.0-linux-x64.tar.xz...
################################################################################################################################################# 100.0%
Computing checksum with sha256sum
Checksums matched!
Now using node v10.1.0 (npm v5.6.0)
Creating default alias: default -> node (-> v10.1.0)
```

## SGX


### Build and Install the Intel(R) SGX Driver

To check if matching kernel headers are installed: 
```
dpkg-query -s linux-headers-$(uname -r)
````

```
spalacio@Qatar01:~$ sudo apt-get install linux-headers-$(uname -r)
Reading package lists... Done
Building dependency tree       
Reading state information... Done
linux-headers-4.15.0-20-generic is already the newest version (4.15.0-20.21).
linux-headers-4.15.0-20-generic set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 10 not upgraded.
```

* References 
https://github.com/intel/linux-sgx-driver/tree/sgx2

```
spalacio@Qatar01:~$ mkdir sgx
spalacio@Qatar01:~$ cd sgx
spalacio@Qatar01:~/sgx$ git clone https://github.com/intel/linux-sgx-driver.git
Cloning into 'linux-sgx-driver'...
remote: Counting objects: 300, done.
remote: Compressing objects: 100% (16/16), done.
remote: Total 300 (delta 9), reused 11 (delta 5), pack-reused 279
Receiving objects: 100% (300/300), 178.30 KiB | 2.23 MiB/s, done.
Resolving deltas: 100% (159/159), done.
spalacio@Qatar01:~/sgx$ cd linux-sgx-driver/
spalacio@Qatar01:~/sgx/linux-sgx-driver$ ls -al
total 148
drwxr-xr-x 4 spalacio spalacio  4096 May 15 17:57 .
drwxr-xr-x 3 spalacio spalacio  4096 May 15 17:57 ..
drwxr-xr-x 8 spalacio spalacio  4096 May 15 17:57 .git
-rw-r--r-- 1 spalacio spalacio    56 May 15 17:57 .gitignore
drwxr-xr-x 2 spalacio spalacio  4096 May 15 17:57 inker2ext
-rw-r--r-- 1 spalacio spalacio   128 May 15 17:57 License.txt
-rw-r--r-- 1 spalacio spalacio   530 May 15 17:57 Makefile
-rw-r--r-- 1 spalacio spalacio  5918 May 15 17:57 README.md
-rw-r--r-- 1 spalacio spalacio  6846 May 15 17:57 sgx_arch.h
-rw-r--r-- 1 spalacio spalacio  5946 May 15 17:57 sgx_asm.h
-rw-r--r-- 1 spalacio spalacio 23612 May 15 17:57 sgx_encl.c
-rw-r--r-- 1 spalacio spalacio  8050 May 15 17:57 sgx.h
-rw-r--r-- 1 spalacio spalacio  7841 May 15 17:57 sgx_ioctl.c
-rw-r--r-- 1 spalacio spalacio 10219 May 15 17:57 sgx_main.c
-rw-r--r-- 1 spalacio spalacio 14432 May 15 17:57 sgx_page_cache.c
-rw-r--r-- 1 spalacio spalacio  4775 May 15 17:57 sgx_user.h
-rw-r--r-- 1 spalacio spalacio  9881 May 15 17:57 sgx_util.c
-rw-r--r-- 1 spalacio spalacio  7094 May 15 17:57 sgx_vma.c
spalacio@Qatar01:~/sgx/linux-sgx-driver$ git branch
* master
spalacio@Qatar01:~/sgx/linux-sgx-driver$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/b1
  remotes/origin/b2
  remotes/origin/master
  remotes/origin/sgx2
spalacio@Qatar01:~/sgx/linux-sgx-driver$ git checkout sgx2
Branch 'sgx2' set up to track remote branch 'sgx2' from 'origin'.
Switched to a new branch 'sgx2'
spalacio@Qatar01:~/sgx/linux-sgx-driver$ git branch
  master
* sgx2
spalacio@Qatar01:~/sgx/linux-sgx-driver$ git pull
Already up to date.
spalacio@Qatar01:~/sgx/linux-sgx-driver$ pwd
/home/spalacio/sgx/linux-sgx-driver
spalacio@Qatar01:~/sgx/linux-sgx-driver$ ls -al
total 168
drwxr-xr-x 4 spalacio spalacio  4096 May 15 17:58 .
drwxr-xr-x 3 spalacio spalacio  4096 May 15 17:57 ..
drwxr-xr-x 8 spalacio spalacio  4096 May 15 17:59 .git
-rw-r--r-- 1 spalacio spalacio    56 May 15 17:57 .gitignore
drwxr-xr-x 2 spalacio spalacio  4096 May 15 17:58 inker2ext
-rw-r--r-- 1 spalacio spalacio   128 May 15 17:57 License.txt
-rw-r--r-- 1 spalacio spalacio   546 May 15 17:58 Makefile
-rw-r--r-- 1 spalacio spalacio  5968 May 15 17:58 README.md
-rw-r--r-- 1 spalacio spalacio  6921 May 15 17:58 sgx_arch.h
-rw-r--r-- 1 spalacio spalacio  5946 May 15 17:57 sgx_asm.h
-rw-r--r-- 1 spalacio spalacio 12122 May 15 17:58 sgx_encl2.c
-rw-r--r-- 1 spalacio spalacio 23861 May 15 17:58 sgx_encl.c
-rw-r--r-- 1 spalacio spalacio  8921 May 15 17:58 sgx.h
-rw-r--r-- 1 spalacio spalacio 11127 May 15 17:58 sgx_ioctl.c
-rw-r--r-- 1 spalacio spalacio 10271 May 15 17:58 sgx_main.c
-rw-r--r-- 1 spalacio spalacio 14452 May 15 17:58 sgx_page_cache.c
-rw-r--r-- 1 spalacio spalacio  5391 May 15 17:58 sgx_user.h
-rw-r--r-- 1 spalacio spalacio 10464 May 15 17:58 sgx_util.c
-rw-r--r-- 1 spalacio spalacio  7207 May 15 17:58 sgx_vma.c
spalacio@Qatar01:~/sgx/linux-sgx-driver$ make
make -C /lib/modules/4.15.0-20-generic/build SUBDIRS=/home/spalacio/sgx/linux-sgx-driver modules
make[1]: Entering directory '/usr/src/linux-headers-4.15.0-20-generic'
Makefile:976: "Cannot use CONFIG_STACK_VALIDATION=y, please install libelf-dev, libelf-devel or elfutils-libelf-devel"
  CC [M]  /home/spalacio/sgx/linux-sgx-driver/sgx_main.o
  CC [M]  /home/spalacio/sgx/linux-sgx-driver/sgx_page_cache.o
  CC [M]  /home/spalacio/sgx/linux-sgx-driver/sgx_ioctl.o
  CC [M]  /home/spalacio/sgx/linux-sgx-driver/sgx_vma.o
  CC [M]  /home/spalacio/sgx/linux-sgx-driver/sgx_util.o
  CC [M]  /home/spalacio/sgx/linux-sgx-driver/sgx_encl.o
  CC [M]  /home/spalacio/sgx/linux-sgx-driver/sgx_encl2.o
  LD [M]  /home/spalacio/sgx/linux-sgx-driver/isgx.o
  Building modules, stage 2.
  MODPOST 1 modules
  CC      /home/spalacio/sgx/linux-sgx-driver/isgx.mod.o
  LD [M]  /home/spalacio/sgx/linux-sgx-driver/isgx.ko
make[1]: Leaving directory '/usr/src/linux-headers-4.15.0-20-generic'
spalacio@Qatar01:~/sgx/linux-sgx-driver$ sudo mkdir -p "/lib/modules/"`uname -r`"/kernel/drivers/intel/sgx"
spalacio@Qatar01:~/sgx/linux-sgx-driver$ sudo cp isgx.ko "/lib/modules/"`uname -r`"/kernel/drivers/intel/sgx"
spalacio@Qatar01:~/sgx/linux-sgx-driver$ sudo sh -c "cat /etc/modules | grep -Fxq isgx || echo isgx >> /etc/modules"
spalacio@Qatar01:~/sgx/linux-sgx-driver$ sudo /sbin/depmod
spalacio@Qatar01:~/sgx/linux-sgx-driver$ sudo /sbin/modprobe isgx
```


```
spalacio@Qatar01:~$ sudo apt-get install build-essential ocaml automake autoconf libtool wget python
[sudo] password for spalacio: 
Reading package lists... Done
Building dependency tree       
Reading state information... Done
wget is already the newest version (1.19.4-1ubuntu2.1).
The following additional packages will be installed:
  autotools-dev camlp4 dpkg-dev fakeroot g++ g++-7 gcc gcc-7 ledit libalgorithm-diff-perl libalgorithm-diff-xs-perl libalgorithm-merge-perl libasan4
  libatomic1 libc-dev-bin libc6-dev libcamlp4-ocaml-dev libcilkrts5 libfakeroot libfindlib-ocaml libfindlib-ocaml-dev libgcc-7-dev libitm1 liblsan0
  libltdl-dev libmpx2 libncurses5-dev libpthread-stubs0-dev libpython-stdlib libquadmath0 libsigsegv2 libstdc++-7-dev libtinfo-dev libtsan0 libubsan0
  libx11-dev libx11-doc libxau-dev libxcb1-dev libxdmcp-dev linux-libc-dev m4 make manpages-dev ocaml-base ocaml-base-nox ocaml-compiler-libs
  ocaml-findlib ocaml-interp ocaml-nox python-minimal python2.7 python2.7-minimal x11proto-core-dev x11proto-dev xorg-sgml-doctools xtrans-dev
Suggested packages:
  autoconf-archive gnu-standards autoconf-doc debian-keyring g++-multilib g++-7-multilib gcc-7-doc libstdc++6-7-dbg gcc-multilib flex bison gcc-doc
  gcc-7-multilib gcc-7-locales libgcc1-dbg libgomp1-dbg libitm1-dbg libatomic1-dbg libasan4-dbg liblsan0-dbg libtsan0-dbg libubsan0-dbg
  libcilkrts5-dbg libmpx2-dbg libquadmath0-dbg glibc-doc libtool-doc ncurses-doc libstdc++-7-doc gfortran | fortran95-compiler gcj-jdk libxcb-doc
  m4-doc make-doc ocaml-doc tuareg-mode | ocaml-mode python-doc python-tk python2.7-doc binfmt-support
The following NEW packages will be installed:
  autoconf automake autotools-dev build-essential camlp4 dpkg-dev fakeroot g++ g++-7 gcc gcc-7 ledit libalgorithm-diff-perl libalgorithm-diff-xs-perl
  libalgorithm-merge-perl libasan4 libatomic1 libc-dev-bin libc6-dev libcamlp4-ocaml-dev libcilkrts5 libfakeroot libfindlib-ocaml libfindlib-ocaml-dev
  libgcc-7-dev libitm1 liblsan0 libltdl-dev libmpx2 libncurses5-dev libpthread-stubs0-dev libpython-stdlib libquadmath0 libsigsegv2 libstdc++-7-dev
  libtinfo-dev libtool libtsan0 libubsan0 libx11-dev libx11-doc libxau-dev libxcb1-dev libxdmcp-dev linux-libc-dev m4 make manpages-dev ocaml
  ocaml-base ocaml-base-nox ocaml-compiler-libs ocaml-findlib ocaml-interp ocaml-nox python python-minimal python2.7 python2.7-minimal
  x11proto-core-dev x11proto-dev xorg-sgml-doctools xtrans-dev
0 upgraded, 63 newly installed, 0 to remove and 10 not upgraded.
Need to get 106 MB of archives.
After this operation, 535 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 python2.7-minimal amd64 2.7.15~rc1-1 [1,292 kB]
Get:2 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 python-minimal amd64 2.7.15~rc1-1 [28.1 kB]
Get:3 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 python2.7 amd64 2.7.15~rc1-1 [238 kB]
Get:4 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libpython-stdlib amd64 2.7.15~rc1-1 [7,620 B]
Get:5 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 python amd64 2.7.15~rc1-1 [140 kB]
Get:6 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libsigsegv2 amd64 2.12-1 [14.7 kB]
Get:7 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 m4 amd64 1.4.18-1 [197 kB]
Get:8 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 autoconf all 2.69-11 [322 kB]
Get:9 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 autotools-dev all 20180224.1 [39.6 kB]
Get:10 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 automake all 1:1.15.1-3ubuntu2 [509 kB]
Get:11 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libc-dev-bin amd64 2.27-3ubuntu1 [71.8 kB]
Get:12 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 linux-libc-dev amd64 4.15.0-20.21 [1,016 kB]
Get:13 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libc6-dev amd64 2.27-3ubuntu1 [2,587 kB]
Get:14 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libitm1 amd64 8-20180414-1ubuntu2 [28.1 kB]
Get:15 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libatomic1 amd64 8-20180414-1ubuntu2 [9,084 B]
Get:16 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libasan4 amd64 7.3.0-16ubuntu3 [359 kB]
Get:17 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 liblsan0 amd64 8-20180414-1ubuntu2 [133 kB]
Get:18 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libtsan0 amd64 8-20180414-1ubuntu2 [289 kB]
Get:19 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libubsan0 amd64 7.3.0-16ubuntu3 [126 kB]
Get:20 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libcilkrts5 amd64 7.3.0-16ubuntu3 [42.5 kB]
Get:21 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libmpx2 amd64 8-20180414-1ubuntu2 [11.7 kB]
Get:22 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libquadmath0 amd64 8-20180414-1ubuntu2 [134 kB]
Get:23 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libgcc-7-dev amd64 7.3.0-16ubuntu3 [2,378 kB]
Get:24 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 gcc-7 amd64 7.3.0-16ubuntu3 [7,445 kB]
Get:25 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 gcc amd64 4:7.3.0-3ubuntu2 [5,192 B]
Get:26 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libstdc++-7-dev amd64 7.3.0-16ubuntu3 [1,461 kB]
Get:27 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 g++-7 amd64 7.3.0-16ubuntu3 [7,566 kB]
Get:28 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 g++ amd64 4:7.3.0-3ubuntu2 [1,576 B]
Get:29 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 make amd64 4.1-9.1ubuntu1 [154 kB]
Get:30 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 dpkg-dev all 1.19.0.5ubuntu2 [607 kB]
Get:31 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 build-essential amd64 12.4ubuntu1 [4,758 B]
Get:32 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-base-nox amd64 4.05.0-10ubuntu1 [544 kB]
Get:33 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libtinfo-dev amd64 6.1-1ubuntu1 [81.1 kB]
Get:34 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libncurses5-dev amd64 6.1-1ubuntu1 [174 kB]
Get:35 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-compiler-libs amd64 4.05.0-10ubuntu1 [18.9 MB]
Get:36 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-interp amd64 4.05.0-10ubuntu1 [3,466 kB]
Get:37 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-nox amd64 4.05.0-10ubuntu1 [27.5 MB]
Get:38 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 libcamlp4-ocaml-dev amd64 4.05+1-2 [16.2 MB]
Get:39 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 camlp4 amd64 4.05+1-2 [4,896 kB]
Get:40 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libfakeroot amd64 1.22-2ubuntu1 [25.9 kB]
Get:41 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 fakeroot amd64 1.22-2ubuntu1 [62.3 kB]
Get:42 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ledit all 2.03-6 [44.9 kB]
Get:43 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libalgorithm-diff-perl all 1.19.03-1 [47.6 kB]
Get:44 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libalgorithm-diff-xs-perl amd64 0.04-5 [11.1 kB]
Get:45 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libalgorithm-merge-perl all 0.08-3 [12.0 kB]
Get:46 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 libfindlib-ocaml amd64 1.7.3-2 [160 kB]
Get:47 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 libfindlib-ocaml-dev amd64 1.7.3-2 [141 kB]
Get:48 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libltdl-dev amd64 2.4.6-2 [162 kB]
Get:49 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libpthread-stubs0-dev amd64 0.3-4 [4,068 B]
Get:50 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libtool all 2.4.6-2 [194 kB]
Get:51 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 xorg-sgml-doctools all 1:1.11-1 [12.9 kB]
Get:52 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 x11proto-dev all 2018.4-4 [251 kB]
Get:53 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 x11proto-core-dev all 2018.4-4 [2,620 B]
Get:54 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libxau-dev amd64 1:1.0.8-1 [11.1 kB]
Get:55 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libxdmcp-dev amd64 1:1.1.2-3 [25.1 kB]
Get:56 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 xtrans-dev all 1.3.5-1 [70.5 kB]
Get:57 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libxcb1-dev amd64 1.13-1 [80.0 kB]
Get:58 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libx11-dev amd64 2:1.6.4-3 [642 kB]
Get:59 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libx11-doc all 2:1.6.4-3 [2,067 kB]
Get:60 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 manpages-dev all 4.15-1 [2,217 kB]
Get:61 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-base amd64 4.05.0-10ubuntu1 [44.9 kB]
Get:62 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml amd64 4.05.0-10ubuntu1 [45.6 kB]
Get:63 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-findlib amd64 1.7.3-2 [366 kB]
Fetched 106 MB in 2s (59.8 MB/s)         
Extracting templates from packages: 100%
Selecting previously unselected package python2.7-minimal.
(Reading database ... 126564 files and directories currently installed.)
Preparing to unpack .../python2.7-minimal_2.7.15~rc1-1_amd64.deb ...
Unpacking python2.7-minimal (2.7.15~rc1-1) ...
Selecting previously unselected package python-minimal.
Preparing to unpack .../python-minimal_2.7.15~rc1-1_amd64.deb ...
Unpacking python-minimal (2.7.15~rc1-1) ...
Selecting previously unselected package python2.7.
Preparing to unpack .../python2.7_2.7.15~rc1-1_amd64.deb ...
Unpacking python2.7 (2.7.15~rc1-1) ...
Selecting previously unselected package libpython-stdlib:amd64.
Preparing to unpack .../libpython-stdlib_2.7.15~rc1-1_amd64.deb ...
Unpacking libpython-stdlib:amd64 (2.7.15~rc1-1) ...
Setting up python2.7-minimal (2.7.15~rc1-1) ...
Linking and byte-compiling packages for runtime python2.7...
Setting up python-minimal (2.7.15~rc1-1) ...
Selecting previously unselected package python.
(Reading database ... 126620 files and directories currently installed.)
Preparing to unpack .../00-python_2.7.15~rc1-1_amd64.deb ...
Unpacking python (2.7.15~rc1-1) ...
Selecting previously unselected package libsigsegv2:amd64.
Preparing to unpack .../01-libsigsegv2_2.12-1_amd64.deb ...
Unpacking libsigsegv2:amd64 (2.12-1) ...
Selecting previously unselected package m4.
Preparing to unpack .../02-m4_1.4.18-1_amd64.deb ...
Unpacking m4 (1.4.18-1) ...
Selecting previously unselected package autoconf.
Preparing to unpack .../03-autoconf_2.69-11_all.deb ...
Unpacking autoconf (2.69-11) ...
Selecting previously unselected package autotools-dev.
Preparing to unpack .../04-autotools-dev_20180224.1_all.deb ...
Unpacking autotools-dev (20180224.1) ...
Selecting previously unselected package automake.
Preparing to unpack .../05-automake_1%3a1.15.1-3ubuntu2_all.deb ...
Unpacking automake (1:1.15.1-3ubuntu2) ...
Selecting previously unselected package libc-dev-bin.
Preparing to unpack .../06-libc-dev-bin_2.27-3ubuntu1_amd64.deb ...
Unpacking libc-dev-bin (2.27-3ubuntu1) ...
Selecting previously unselected package linux-libc-dev:amd64.
Preparing to unpack .../07-linux-libc-dev_4.15.0-20.21_amd64.deb ...
Unpacking linux-libc-dev:amd64 (4.15.0-20.21) ...
Selecting previously unselected package libc6-dev:amd64.
Preparing to unpack .../08-libc6-dev_2.27-3ubuntu1_amd64.deb ...
Unpacking libc6-dev:amd64 (2.27-3ubuntu1) ...
Selecting previously unselected package libitm1:amd64.
Preparing to unpack .../09-libitm1_8-20180414-1ubuntu2_amd64.deb ...
Unpacking libitm1:amd64 (8-20180414-1ubuntu2) ...
Selecting previously unselected package libatomic1:amd64.
Preparing to unpack .../10-libatomic1_8-20180414-1ubuntu2_amd64.deb ...
Unpacking libatomic1:amd64 (8-20180414-1ubuntu2) ...
Selecting previously unselected package libasan4:amd64.
Preparing to unpack .../11-libasan4_7.3.0-16ubuntu3_amd64.deb ...
Unpacking libasan4:amd64 (7.3.0-16ubuntu3) ...
Selecting previously unselected package liblsan0:amd64.
Preparing to unpack .../12-liblsan0_8-20180414-1ubuntu2_amd64.deb ...
Unpacking liblsan0:amd64 (8-20180414-1ubuntu2) ...
Selecting previously unselected package libtsan0:amd64.
Preparing to unpack .../13-libtsan0_8-20180414-1ubuntu2_amd64.deb ...
Unpacking libtsan0:amd64 (8-20180414-1ubuntu2) ...
Selecting previously unselected package libubsan0:amd64.
Preparing to unpack .../14-libubsan0_7.3.0-16ubuntu3_amd64.deb ...
Unpacking libubsan0:amd64 (7.3.0-16ubuntu3) ...
Selecting previously unselected package libcilkrts5:amd64.
Preparing to unpack .../15-libcilkrts5_7.3.0-16ubuntu3_amd64.deb ...
Unpacking libcilkrts5:amd64 (7.3.0-16ubuntu3) ...
Selecting previously unselected package libmpx2:amd64.
Preparing to unpack .../16-libmpx2_8-20180414-1ubuntu2_amd64.deb ...
Unpacking libmpx2:amd64 (8-20180414-1ubuntu2) ...
Selecting previously unselected package libquadmath0:amd64.
Preparing to unpack .../17-libquadmath0_8-20180414-1ubuntu2_amd64.deb ...
Unpacking libquadmath0:amd64 (8-20180414-1ubuntu2) ...
Selecting previously unselected package libgcc-7-dev:amd64.
Preparing to unpack .../18-libgcc-7-dev_7.3.0-16ubuntu3_amd64.deb ...
Unpacking libgcc-7-dev:amd64 (7.3.0-16ubuntu3) ...
Selecting previously unselected package gcc-7.
Preparing to unpack .../19-gcc-7_7.3.0-16ubuntu3_amd64.deb ...
Unpacking gcc-7 (7.3.0-16ubuntu3) ...
Selecting previously unselected package gcc.
Preparing to unpack .../20-gcc_4%3a7.3.0-3ubuntu2_amd64.deb ...
Unpacking gcc (4:7.3.0-3ubuntu2) ...
Selecting previously unselected package libstdc++-7-dev:amd64.
Preparing to unpack .../21-libstdc++-7-dev_7.3.0-16ubuntu3_amd64.deb ...
Unpacking libstdc++-7-dev:amd64 (7.3.0-16ubuntu3) ...
Selecting previously unselected package g++-7.
Preparing to unpack .../22-g++-7_7.3.0-16ubuntu3_amd64.deb ...
Unpacking g++-7 (7.3.0-16ubuntu3) ...
Selecting previously unselected package g++.
Preparing to unpack .../23-g++_4%3a7.3.0-3ubuntu2_amd64.deb ...
Unpacking g++ (4:7.3.0-3ubuntu2) ...
Selecting previously unselected package make.
Preparing to unpack .../24-make_4.1-9.1ubuntu1_amd64.deb ...
Unpacking make (4.1-9.1ubuntu1) ...
Selecting previously unselected package dpkg-dev.
Preparing to unpack .../25-dpkg-dev_1.19.0.5ubuntu2_all.deb ...
Unpacking dpkg-dev (1.19.0.5ubuntu2) ...
Selecting previously unselected package build-essential.
Preparing to unpack .../26-build-essential_12.4ubuntu1_amd64.deb ...
Unpacking build-essential (12.4ubuntu1) ...
Selecting previously unselected package ocaml-base-nox.
Preparing to unpack .../27-ocaml-base-nox_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml-base-nox (4.05.0-10ubuntu1) ...
Selecting previously unselected package libtinfo-dev:amd64.
Preparing to unpack .../28-libtinfo-dev_6.1-1ubuntu1_amd64.deb ...
Unpacking libtinfo-dev:amd64 (6.1-1ubuntu1) ...
Selecting previously unselected package libncurses5-dev:amd64.
Preparing to unpack .../29-libncurses5-dev_6.1-1ubuntu1_amd64.deb ...
Unpacking libncurses5-dev:amd64 (6.1-1ubuntu1) ...
Selecting previously unselected package ocaml-compiler-libs.
Preparing to unpack .../30-ocaml-compiler-libs_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml-compiler-libs (4.05.0-10ubuntu1) ...
Selecting previously unselected package ocaml-interp.
Preparing to unpack .../31-ocaml-interp_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml-interp (4.05.0-10ubuntu1) ...
Selecting previously unselected package ocaml-nox.
Preparing to unpack .../32-ocaml-nox_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml-nox (4.05.0-10ubuntu1) ...
Selecting previously unselected package libcamlp4-ocaml-dev.
Preparing to unpack .../33-libcamlp4-ocaml-dev_4.05+1-2_amd64.deb ...
Unpacking libcamlp4-ocaml-dev (4.05+1-2) ...
Selecting previously unselected package camlp4.
Preparing to unpack .../34-camlp4_4.05+1-2_amd64.deb ...
Unpacking camlp4 (4.05+1-2) ...
Selecting previously unselected package libfakeroot:amd64.
Preparing to unpack .../35-libfakeroot_1.22-2ubuntu1_amd64.deb ...
Unpacking libfakeroot:amd64 (1.22-2ubuntu1) ...
Selecting previously unselected package fakeroot.
Preparing to unpack .../36-fakeroot_1.22-2ubuntu1_amd64.deb ...
Unpacking fakeroot (1.22-2ubuntu1) ...
Selecting previously unselected package ledit.
Preparing to unpack .../37-ledit_2.03-6_all.deb ...
Unpacking ledit (2.03-6) ...
Selecting previously unselected package libalgorithm-diff-perl.
Preparing to unpack .../38-libalgorithm-diff-perl_1.19.03-1_all.deb ...
Unpacking libalgorithm-diff-perl (1.19.03-1) ...
Selecting previously unselected package libalgorithm-diff-xs-perl.
Preparing to unpack .../39-libalgorithm-diff-xs-perl_0.04-5_amd64.deb ...
Unpacking libalgorithm-diff-xs-perl (0.04-5) ...
Selecting previously unselected package libalgorithm-merge-perl.
Preparing to unpack .../40-libalgorithm-merge-perl_0.08-3_all.deb ...
Unpacking libalgorithm-merge-perl (0.08-3) ...
Selecting previously unselected package libfindlib-ocaml.
Preparing to unpack .../41-libfindlib-ocaml_1.7.3-2_amd64.deb ...
Unpacking libfindlib-ocaml (1.7.3-2) ...
Selecting previously unselected package libfindlib-ocaml-dev.
Preparing to unpack .../42-libfindlib-ocaml-dev_1.7.3-2_amd64.deb ...
Unpacking libfindlib-ocaml-dev (1.7.3-2) ...
Selecting previously unselected package libltdl-dev:amd64.
Preparing to unpack .../43-libltdl-dev_2.4.6-2_amd64.deb ...
Unpacking libltdl-dev:amd64 (2.4.6-2) ...
Selecting previously unselected package libpthread-stubs0-dev:amd64.
Preparing to unpack .../44-libpthread-stubs0-dev_0.3-4_amd64.deb ...
Unpacking libpthread-stubs0-dev:amd64 (0.3-4) ...
Selecting previously unselected package libtool.
Preparing to unpack .../45-libtool_2.4.6-2_all.deb ...
Unpacking libtool (2.4.6-2) ...
Selecting previously unselected package xorg-sgml-doctools.
Preparing to unpack .../46-xorg-sgml-doctools_1%3a1.11-1_all.deb ...
Unpacking xorg-sgml-doctools (1:1.11-1) ...
Selecting previously unselected package x11proto-dev.
Preparing to unpack .../47-x11proto-dev_2018.4-4_all.deb ...
Unpacking x11proto-dev (2018.4-4) ...
Selecting previously unselected package x11proto-core-dev.
Preparing to unpack .../48-x11proto-core-dev_2018.4-4_all.deb ...
Unpacking x11proto-core-dev (2018.4-4) ...
Selecting previously unselected package libxau-dev:amd64.
Preparing to unpack .../49-libxau-dev_1%3a1.0.8-1_amd64.deb ...
Unpacking libxau-dev:amd64 (1:1.0.8-1) ...
Selecting previously unselected package libxdmcp-dev:amd64.
Preparing to unpack .../50-libxdmcp-dev_1%3a1.1.2-3_amd64.deb ...
Unpacking libxdmcp-dev:amd64 (1:1.1.2-3) ...
Selecting previously unselected package xtrans-dev.
Preparing to unpack .../51-xtrans-dev_1.3.5-1_all.deb ...
Unpacking xtrans-dev (1.3.5-1) ...
Selecting previously unselected package libxcb1-dev:amd64.
Preparing to unpack .../52-libxcb1-dev_1.13-1_amd64.deb ...
Unpacking libxcb1-dev:amd64 (1.13-1) ...
Selecting previously unselected package libx11-dev:amd64.
Preparing to unpack .../53-libx11-dev_2%3a1.6.4-3_amd64.deb ...
Unpacking libx11-dev:amd64 (2:1.6.4-3) ...
Selecting previously unselected package libx11-doc.
Preparing to unpack .../54-libx11-doc_2%3a1.6.4-3_all.deb ...
Unpacking libx11-doc (2:1.6.4-3) ...
Selecting previously unselected package manpages-dev.
Preparing to unpack .../55-manpages-dev_4.15-1_all.deb ...
Unpacking manpages-dev (4.15-1) ...
Selecting previously unselected package ocaml-base.
Preparing to unpack .../56-ocaml-base_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml-base (4.05.0-10ubuntu1) ...
Selecting previously unselected package ocaml.
Preparing to unpack .../57-ocaml_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml (4.05.0-10ubuntu1) ...
Selecting previously unselected package ocaml-findlib.
Preparing to unpack .../58-ocaml-findlib_1.7.3-2_amd64.deb ...
Unpacking ocaml-findlib (1.7.3-2) ...
Setting up libquadmath0:amd64 (8-20180414-1ubuntu2) ...
Setting up libatomic1:amd64 (8-20180414-1ubuntu2) ...
Setting up make (4.1-9.1ubuntu1) ...
Setting up libltdl-dev:amd64 (2.4.6-2) ...
Processing triggers for mime-support (3.60ubuntu1) ...
Setting up libasan4:amd64 (7.3.0-16ubuntu3) ...
Processing triggers for desktop-file-utils (0.23-1ubuntu3) ...
Setting up libsigsegv2:amd64 (2.12-1) ...
Setting up libpthread-stubs0-dev:amd64 (0.3-4) ...
Setting up libcilkrts5:amd64 (7.3.0-16ubuntu3) ...
Processing triggers for install-info (6.5.0.dfsg.1-2) ...
Setting up libubsan0:amd64 (7.3.0-16ubuntu3) ...
Setting up libtsan0:amd64 (8-20180414-1ubuntu2) ...
Setting up xorg-sgml-doctools (1:1.11-1) ...
Setting up ocaml-base-nox (4.05.0-10ubuntu1) ...
Setting up linux-libc-dev:amd64 (4.15.0-20.21) ...
Setting up libtinfo-dev:amd64 (6.1-1ubuntu1) ...
Setting up python2.7 (2.7.15~rc1-1) ...
Setting up m4 (1.4.18-1) ...
Setting up x11proto-dev (2018.4-4) ...
Setting up liblsan0:amd64 (8-20180414-1ubuntu2) ...
Setting up libpython-stdlib:amd64 (2.7.15~rc1-1) ...
Setting up libmpx2:amd64 (8-20180414-1ubuntu2) ...
Setting up xtrans-dev (1.3.5-1) ...
Setting up dpkg-dev (1.19.0.5ubuntu2) ...
Setting up ocaml-base (4.05.0-10ubuntu1) ...
Setting up libxdmcp-dev:amd64 (1:1.1.2-3) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Setting up autotools-dev (20180224.1) ...
Setting up libfakeroot:amd64 (1.22-2ubuntu1) ...
Setting up libalgorithm-diff-perl (1.19.03-1) ...
Setting up libx11-doc (2:1.6.4-3) ...
Processing triggers for man-db (2.8.3-2) ...
Setting up libc-dev-bin (2.27-3ubuntu1) ...
Processing triggers for gnome-menus (3.13.3-11ubuntu1) ...
Setting up manpages-dev (4.15-1) ...
Setting up libc6-dev:amd64 (2.27-3ubuntu1) ...
Setting up libfindlib-ocaml (1.7.3-2) ...
Setting up ocaml-findlib (1.7.3-2) ...
Setting up libitm1:amd64 (8-20180414-1ubuntu2) ...
Setting up python (2.7.15~rc1-1) ...
Setting up x11proto-core-dev (2018.4-4) ...
Setting up ledit (2.03-6) ...
update-alternatives: using /usr/bin/ledit to provide /usr/bin/readline-editor (readline-editor) in auto mode
Setting up libxau-dev:amd64 (1:1.0.8-1) ...
Setting up autoconf (2.69-11) ...
Setting up fakeroot (1.22-2ubuntu1) ...
update-alternatives: using /usr/bin/fakeroot-sysv to provide /usr/bin/fakeroot (fakeroot) in auto mode
Setting up libgcc-7-dev:amd64 (7.3.0-16ubuntu3) ...
Setting up libstdc++-7-dev:amd64 (7.3.0-16ubuntu3) ...
Setting up libncurses5-dev:amd64 (6.1-1ubuntu1) ...
Setting up libalgorithm-merge-perl (0.08-3) ...
Setting up libalgorithm-diff-xs-perl (0.04-5) ...
Setting up automake (1:1.15.1-3ubuntu2) ...
update-alternatives: using /usr/bin/automake-1.15 to provide /usr/bin/automake (automake) in auto mode
Setting up libxcb1-dev:amd64 (1.13-1) ...
Setting up libx11-dev:amd64 (2:1.6.4-3) ...
Setting up gcc-7 (7.3.0-16ubuntu3) ...
Setting up g++-7 (7.3.0-16ubuntu3) ...
Setting up gcc (4:7.3.0-3ubuntu2) ...
Setting up g++ (4:7.3.0-3ubuntu2) ...
update-alternatives: using /usr/bin/g++ to provide /usr/bin/c++ (c++) in auto mode
Setting up libtool (2.4.6-2) ...
Setting up build-essential (12.4ubuntu1) ...
Setting up ocaml-compiler-libs (4.05.0-10ubuntu1) ...
Setting up ocaml-interp (4.05.0-10ubuntu1) ...
Setting up ocaml-nox (4.05.0-10ubuntu1) ...
Setting up libcamlp4-ocaml-dev (4.05+1-2) ...
Setting up ocaml (4.05.0-10ubuntu1) ...
Setting up camlp4 (4.05+1-2) ...
Setting up libfindlib-ocaml-dev (1.7.3-2) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
```

```
spalacio@Qatar01:~$ sudo apt-get install libssl-dev libcurl4-openssl-dev protobuf-compiler libprotobuf-dev
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  libprotobuf-lite10 libprotoc10 libssl-doc zlib1g-dev
Suggested packages:
  libcurl4-doc libidn11-dev libkrb5-dev libldap2-dev librtmp-dev libssh2-1-dev pkg-config
The following NEW packages will be installed:
  libcurl4-openssl-dev libprotobuf-dev libprotobuf-lite10 libprotoc10 libssl-dev libssl-doc protobuf-compiler zlib1g-dev
0 upgraded, 8 newly installed, 0 to remove and 10 not upgraded.
Need to get 4,746 kB of archives.
After this operation, 24.3 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libcurl4-openssl-dev amd64 7.58.0-2ubuntu3 [295 kB]
Get:2 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libprotobuf-lite10 amd64 3.0.0-9.1ubuntu1 [97.7 kB]
Get:3 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libprotoc10 amd64 3.0.0-9.1ubuntu1 [566 kB]
Get:4 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libssl-dev amd64 1.1.0g-2ubuntu4 [1,372 kB]
Get:5 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libssl-doc all 1.1.0g-2ubuntu4 [1,256 kB]
Get:6 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 zlib1g-dev amd64 1:1.2.11.dfsg-0ubuntu2 [176 kB]
Get:7 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libprotobuf-dev amd64 3.0.0-9.1ubuntu1 [959 kB]
Get:8 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 protobuf-compiler amd64 3.0.0-9.1ubuntu1 [24.5 kB]
Fetched 4,746 kB in 0s (11.4 MB/s)            
Selecting previously unselected package libcurl4-openssl-dev:amd64.
(Reading database ... 135709 files and directories currently installed.)
Preparing to unpack .../0-libcurl4-openssl-dev_7.58.0-2ubuntu3_amd64.deb ...
Unpacking libcurl4-openssl-dev:amd64 (7.58.0-2ubuntu3) ...
Selecting previously unselected package libprotobuf-lite10:amd64.
Preparing to unpack .../1-libprotobuf-lite10_3.0.0-9.1ubuntu1_amd64.deb ...
Unpacking libprotobuf-lite10:amd64 (3.0.0-9.1ubuntu1) ...
Selecting previously unselected package libprotoc10:amd64.
Preparing to unpack .../2-libprotoc10_3.0.0-9.1ubuntu1_amd64.deb ...
Unpacking libprotoc10:amd64 (3.0.0-9.1ubuntu1) ...
Selecting previously unselected package libssl-dev:amd64.
Preparing to unpack .../3-libssl-dev_1.1.0g-2ubuntu4_amd64.deb ...
Unpacking libssl-dev:amd64 (1.1.0g-2ubuntu4) ...
Selecting previously unselected package libssl-doc.
Preparing to unpack .../4-libssl-doc_1.1.0g-2ubuntu4_all.deb ...
Unpacking libssl-doc (1.1.0g-2ubuntu4) ...
Selecting previously unselected package zlib1g-dev:amd64.
Preparing to unpack .../5-zlib1g-dev_1%3a1.2.11.dfsg-0ubuntu2_amd64.deb ...
Unpacking zlib1g-dev:amd64 (1:1.2.11.dfsg-0ubuntu2) ...
Selecting previously unselected package libprotobuf-dev:amd64.
Preparing to unpack .../6-libprotobuf-dev_3.0.0-9.1ubuntu1_amd64.deb ...
Unpacking libprotobuf-dev:amd64 (3.0.0-9.1ubuntu1) ...
Selecting previously unselected package protobuf-compiler.
Preparing to unpack .../7-protobuf-compiler_3.0.0-9.1ubuntu1_amd64.deb ...
Unpacking protobuf-compiler (3.0.0-9.1ubuntu1) ...
Setting up libssl-dev:amd64 (1.1.0g-2ubuntu4) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Processing triggers for man-db (2.8.3-2) ...
Setting up libssl-doc (1.1.0g-2ubuntu4) ...
Setting up libprotobuf-lite10:amd64 (3.0.0-9.1ubuntu1) ...
Setting up libprotoc10:amd64 (3.0.0-9.1ubuntu1) ...
Setting up libcurl4-openssl-dev:amd64 (7.58.0-2ubuntu3) ...
Setting up zlib1g-dev:amd64 (1:1.2.11.dfsg-0ubuntu2) ...
Setting up protobuf-compiler (3.0.0-9.1ubuntu1) ...
Setting up libprotobuf-dev:amd64 (3.0.0-9.1ubuntu1) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
```

## Build the Intel(R) SGX SDK and Intel(R) SGX PSW


```
spalacio@Qatar01:~/sgx$ git clone https://github.com/intel/linux-sgx.git
Cloning into 'linux-sgx'...
remote: Counting objects: 17411, done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 17411 (delta 0), reused 0 (delta 0), pack-reused 17401
Receiving objects: 100% (17411/17411), 19.31 MiB | 29.04 MiB/s, done.
Resolving deltas: 100% (9479/9479), done.
spalacio@Qatar01:~/sgx$ cd linux-sgx
spalacio@Qatar01:~/sgx/linux-sgx$ pwd
/home/spalacio/sgx/linux-sgx
spalacio@Qatar01:~/sgx/linux-sgx$ ls -al
total 172
drwxr-xr-x 11 spalacio spalacio  4096 May 15 18:05 .
drwxr-xr-x  4 spalacio spalacio  4096 May 15 18:05 ..
-rw-r--r--  1 spalacio spalacio  6432 May 15 18:05 buildenv.mk
drwxr-xr-x  2 spalacio spalacio  4096 May 15 18:05 build-scripts
drwxr-xr-x  5 spalacio spalacio  4096 May 15 18:05 common
-rw-r--r--  1 spalacio spalacio  3630 May 15 18:05 CONTRIBUTING.md
-rwxr-xr-x  1 spalacio spalacio  2754 May 15 18:05 download_prebuilt.sh
drwxr-xr-x 10 spalacio spalacio  4096 May 15 18:05 external
drwxr-xr-x  8 spalacio spalacio  4096 May 15 18:05 .git
-rw-r--r--  1 spalacio spalacio   150 May 15 18:05 .gitignore
-rw-r--r--  1 spalacio spalacio 86687 May 15 18:05 License.txt
drwxr-xr-x  3 spalacio spalacio  4096 May 15 18:05 linux
drwxr-xr-x  4 spalacio spalacio  4096 May 15 18:05 Linux_SGXEclipsePlugin
-rw-r--r--  1 spalacio spalacio  2504 May 15 18:05 Makefile
drwxr-xr-x  5 spalacio spalacio  4096 May 15 18:05 psw
-rw-r--r--  1 spalacio spalacio 12850 May 15 18:05 README.md
drwxr-xr-x  9 spalacio spalacio  4096 May 15 18:05 SampleCode
drwxr-xr-x 28 spalacio spalacio  4096 May 15 18:05 sdk
spalacio@Qatar01:~/sgx/linux-sgx$ ./download_prebuilt.sh
--2018-05-15 18:06:23--  https://download.01.org/intel-sgx/linux-2.1.3//optimized_libs-2.1.3.tar
Resolving download.01.org (download.01.org)... 96.17.33.204, 2600:1408:20:48e::ae6, 2600:1408:20:492::ae6
Connecting to download.01.org (download.01.org)|96.17.33.204|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 80209920 (76M) [application/x-tar]
Saving to: ‘./optimized_libs-2.1.3.tar’

optimized_libs-2.1.3.tar                 100%[===============================================================================>]  76.49M  4.90MB/s    in 16s     

2018-05-15 18:06:39 (4.81 MB/s) - ‘./optimized_libs-2.1.3.tar’ saved [80209920/80209920]

b8091d8ad9ea91949610468944b2604c858833f70099c7d369234acd3d62c774  ./optimized_libs-2.1.3.tar
--2018-05-15 18:06:39--  https://download.01.org/intel-sgx/linux-2.1.3//prebuilt-ae-2.1.3.tar
Resolving download.01.org (download.01.org)... 96.17.33.204, 2600:1408:20:48e::ae6, 2600:1408:20:492::ae6
Connecting to download.01.org (download.01.org)|96.17.33.204|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 5068800 (4.8M) [application/x-tar]
Saving to: ‘./prebuilt-ae-2.1.3.tar’

prebuilt-ae-2.1.3.tar                    100%[===============================================================================>]   4.83M  4.27MB/s    in 1.1s    

2018-05-15 18:06:41 (4.27 MB/s) - ‘./prebuilt-ae-2.1.3.tar’ saved [5068800/5068800]

022fadd5a72234282176c09695c08b755defcffb82ea47b7dd9337c2f43b8378  ./prebuilt-ae-2.1.3.tar
~/sgx/linux-sgx ~/sgx/linux-sgx
~/sgx/linux-sgx

```

```
make sdk_install_pkg

.
.
.
package/include/libcxx/limits
package/include/libcxx/cinttypes
package/include/libcxx/string
package/include/libcxx/__sso_allocator
package/include/libcxx/regex
package/include/sgx_report.h
package/include/sgx.h
package/include/sgx_eid.h
package/include/sgx_thread.h
scripts/
scripts/installConfig
scripts/install.sh
Generated sdk installer: ./linux/installer/bin/sgx_linux_x64_sdk_2.1.3.44322.bin

```

## Install the Intel(R) SGX SDK

```
spalacio@Qatar01:~/sgx/linux-sgx$ sudo apt-get install build-essential python
Reading package lists... Done
Building dependency tree       
Reading state information... Done
build-essential is already the newest version (12.4ubuntu1).
python is already the newest version (2.7.15~rc1-1).
0 upgraded, 0 newly installed, 0 to remove and 10 not upgraded.
spalacio@Qatar01:~/sgx/linux-sgx$ cd linux/installer/bin
spalacio@Qatar01:~/sgx/linux-sgx/linux/installer/bin$ ./sgx_linux_x64_sdk_${version}.bin
bash: ./sgx_linux_x64_sdk_.bin: No such file or directory
spalacio@Qatar01:~/sgx/linux-sgx/linux/installer/bin$ ls -al
total 14436
drwxr-xr-x 2 spalacio spalacio     4096 May 15 18:43 .
drwxr-xr-x 4 spalacio spalacio     4096 May 15 18:05 ..
-rwxr-xr-x 1 spalacio spalacio     3723 May 15 18:05 build-installpkg.sh
-rwxr-xr-x 1 spalacio spalacio     3936 May 15 18:05 install-sgx-psw.bin.tmpl
-rwxr-xr-x 1 spalacio spalacio     6170 May 15 18:05 install-sgx-sdk.bin.tmpl
-rwxr-xr-x 1 spalacio spalacio 14754923 May 15 18:43 sgx_linux_x64_sdk_2.1.3.44322.bin
spalacio@Qatar01:~/sgx/linux-sgx/linux/installer/bin$ ./sgx_linux_x64_sdk_2.1.3.44322.bin

Do you want to install in current directory? [yes/no] : yes
Unpacking Intel SGX SDK ... done.
Verifying the integrity of the install package ... done.
Installing Intel SGX SDK ... done.
/tmp/sgx-sdk-afqfaO ~/sgx/linux-sgx/linux/installer/bin
install -d /home/spalacio/sgx/linux-sgx/linux/installer/bin/sgxsdk
install -d /home/spalacio/sgx/linux-sgx/linux/installer/bin/sgxsdk/scripts
cp -r package/* /home/spalacio/sgx/linux-sgx/linux/installer/bin/sgxsdk
install scripts/* /home/spalacio/sgx/linux-sgx/linux/installer/bin/sgxsdk/scripts
~/sgx/linux-sgx/linux/installer/bin
uninstall.sh script generated in /home/spalacio/sgx/linux-sgx/linux/installer/bin/sgxsdk

Installation is successful! The SDK package can be found in /home/spalacio/sgx/linux-sgx/linux/installer/bin/sgxsdk

Please set the environment variables with below command:

source /home/spalacio/sgx/linux-sgx/linux/installer/bin/sgxsdk/environment
spalacio@Qatar01:~/sgx/linux-sgx/linux/installer/bin$ source /home/spalacio/sgx/linux-sgx/linux/installer/bin/sgxsdk/environment

```

### Tests

#### First
```
spalacio@Qatar01:~/sgx/linux-sgx/linux/installer/bin/sgxsdk$ vi environment
spalacio@Qatar01:~/sgx/linux-sgx/linux/installer/bin/sgxsdk$ source environment
```

```
source ~/sgx/linux-sgx/linux/installer/bin/sgxsdk/environment
```

#### Second
```
/home/spalacio/sgx/linux-sgx/linux/installer/bin/sgxsdk/SampleCode/LocalAttestation
➜  LocalAttestation git:(master) ✗ make clean
➜  LocalAttestation git:(master) ✗ make SGX_MODE=SIM
spalacio@Qatar01:~/sgx/linux-sgx$ cd SampleCode/LocalAttestation
spalacio@Qatar01:~/sgx/linux-sgx/SampleCode/LocalAttestation$ make SGX_MODE=SIM
GEN  =>  LocalAttestationCode/LocalAttestationCode_t.c
CC   <=  LocalAttestationCode/LocalAttestationCode_t.c
CC   <= LocalAttestationCode/EnclaveMessageExchange.cpp
GEN  =>  libLocalAttestation_Trusted.a
CC   <=  Untrusted_LocalAttestation/UntrustedEnclaveMessageExchange.cpp
GEN  =>  libLocalAttestation_unTrusted.a
GEN  =>  Enclave1/Enclave1_t.c
CC   <=  Enclave1/Enclave1_t.c
CXX  <=  Enclave1/Utility_E1.cpp
CXX  <=  Enclave1/Enclave1.cpp
LINK =>  Enclave1.so
<EnclaveConfiguration>
    <ProdID>0</ProdID>
    <ISVSVN>0</ISVSVN>
    <StackMaxSize>0x40000</StackMaxSize>
    <HeapMaxSize>0x100000</HeapMaxSize>
    <TCSNum>1</TCSNum>
    <TCSPolicy>1</TCSPolicy>
    <!-- Recommend changing 'DisableDebug' to 1 to make the enclave undebuggable for enclave release -->
    <DisableDebug>0</DisableDebug>
    <MiscSelect>0</MiscSelect>
    <MiscMask>0xFFFFFFFF</MiscMask>
</EnclaveConfiguration>
tcs_num 1, tcs_max_num 1, tcs_min_pool 1
The required memory is 2019328B.
Succeed.
SIGN =>  libenclave1.so
GEN  =>  Enclave2/Enclave2_t.c
CC   <=  Enclave2/Enclave2_t.c
CXX  <=  Enclave2/Enclave2.cpp
CXX  <=  Enclave2/Utility_E2.cpp
LINK =>  Enclave2.so
<EnclaveConfiguration>
    <ProdID>0</ProdID>
    <ISVSVN>0</ISVSVN>
    <StackMaxSize>0x40000</StackMaxSize>
    <HeapMaxSize>0x100000</HeapMaxSize>
    <TCSNum>1</TCSNum>
    <TCSPolicy>1</TCSPolicy>
    <!-- Recommend changing 'DisableDebug' to 1 to make the enclave undebuggable for enclave release -->
    <DisableDebug>0</DisableDebug>
    <MiscSelect>0</MiscSelect>
    <MiscMask>0xFFFFFFFF</MiscMask>
</EnclaveConfiguration>
tcs_num 1, tcs_max_num 1, tcs_min_pool 1
The required memory is 2019328B.
Succeed.
SIGN =>  libenclave2.so
GEN  =>  Enclave3/Enclave3_t.c
CC   <=  Enclave3/Enclave3_t.c
CXX  <=  Enclave3/Enclave3.cpp
CXX  <=  Enclave3/Utility_E3.cpp
LINK =>  Enclave3.so
<EnclaveConfiguration>
    <ProdID>0</ProdID>
    <ISVSVN>0</ISVSVN>
    <StackMaxSize>0x40000</StackMaxSize>
    <HeapMaxSize>0x100000</HeapMaxSize>
    <TCSNum>1</TCSNum>
    <TCSPolicy>1</TCSPolicy>
    <!-- Recommend changing 'DisableDebug' to 1 to make the enclave undebuggable for enclave release -->
    <DisableDebug>0</DisableDebug>
    <MiscSelect>0</MiscSelect>
    <MiscMask>0xFFFFFFFF</MiscMask>
</EnclaveConfiguration>
tcs_num 1, tcs_max_num 1, tcs_min_pool 1
The required memory is 2019328B.
Succeed.
SIGN =>  libenclave3.so
GEN  =>  Enclave1/Enclave1_u.c
CC   <=  Enclave1/Enclave1_u.c
GEN  =>  Enclave2/Enclave2_u.c
CC   <=  Enclave2/Enclave2_u.c
GEN  =>  Enclave3/Enclave3_u.c
CC   <=  Enclave3/Enclave3_u.c
CXX  <=  App/App.cpp
LINK =>  app
The project has been built in debug simulation mode.
spalacio@Qatar01:~/sgx/linux-sgx/SampleCode/LocalAttestation$ ./app

Available Enclaves
Enclave1 - EnclaveID 54700000002
Enclave2 - EnclaveID 54700000003
Enclave3 - EnclaveID 54700000004

Secure Channel Establishment between Source (E1) and Destination (E2) Enclaves successful !!!

Enclave to Enclave Call between Source (E1) and Destination (E2) Enclaves successful !!!

Message Exchange between Source (E1) and Destination (E2) Enclaves successful !!!

Secure Channel Establishment between Source (E1) and Destination (E3) Enclaves successful !!!

Enclave to Enclave Call between Source (E1) and Destination (E3) Enclaves successful !!!

Message Exchange between Source (E1) and Destination (E3) Enclaves successful !!!

Secure Channel Establishment between Source (E2) and Destination (E3) Enclaves successful !!!

Enclave to Enclave Call between Source (E2) and Destination (E3) Enclaves successful !!!

Message Exchange between Source (E2) and Destination (E3) Enclaves successful !!!

Secure Channel Establishment between Source (E3) and Destination (E1) Enclaves successful !!!

Enclave to Enclave Call between Source (E3) and Destination (E1) Enclaves successful !!!

Message Exchange between Source (E3) and Destination (E1) Enclaves successful !!!

Close Session between Source (E1) and Destination (E2) Enclaves successful !!!

Close Session between Source (E1) and Destination (E3) Enclaves successful !!!

Close Session between Source (E2) and Destination (E3) Enclaves successful !!!

Close Session between Source (E3) and Destination (E1) Enclaves successful !!!

Hit a key....
 d

```


```
➜  LocalAttestation git:(master) ✗ make clean
➜  LocalAttestation git:(master) ✗ make SGX_MODE=SIM
GEN  =>  LocalAttestationCode/LocalAttestationCode_t.c
CC   <=  LocalAttestationCode/LocalAttestationCode_t.c
CC   <= LocalAttestationCode/EnclaveMessageExchange.cpp
GEN  =>  libLocalAttestation_Trusted.a
CC   <=  Untrusted_LocalAttestation/UntrustedEnclaveMessageExchange.cpp
GEN  =>  libLocalAttestation_unTrusted.a
CC   <=  Enclave1/Enclave1_t.c                                                                                                 [0/1808]
CXX  <=  Enclave1/Utility_E1.cpp
CXX  <=  Enclave1/Enclave1.cpp
LINK =>  Enclave1.so
<EnclaveConfiguration>
    <ProdID>0</ProdID>
    <ISVSVN>0</ISVSVN>
    <StackMaxSize>0x40000</StackMaxSize>
    <HeapMaxSize>0x100000</HeapMaxSize>
    <TCSNum>1</TCSNum>
    <TCSPolicy>1</TCSPolicy>
    <!-- Recommend changing 'DisableDebug' to 1 to make the enclave undebuggable for enclave release -->
    <DisableDebug>0</DisableDebug>
    <MiscSelect>0</MiscSelect>
    <MiscMask>0xFFFFFFFF</MiscMask>
</EnclaveConfiguration>
tcs_num 1, tcs_max_num 1, tcs_min_pool 1
The required memory is 2019328B.
Succeed.
SIGN =>  libenclave1.so
GEN  =>  Enclave2/Enclave2_t.c
CC   <=  Enclave2/Enclave2_t.c
CXX  <=  Enclave2/Enclave2.cpp
CXX  <=  Enclave2/Utility_E2.cpp
LINK =>  Enclave2.so
<EnclaveConfiguration>
    <ProdID>0</ProdID>
    <ISVSVN>0</ISVSVN>
    <StackMaxSize>0x40000</StackMaxSize>
    <HeapMaxSize>0x100000</HeapMaxSize>
    <TCSNum>1</TCSNum>
    <TCSPolicy>1</TCSPolicy>
    <!-- Recommend changing 'DisableDebug' to 1 to make the enclave undebuggable for enclave release -->
    <DisableDebug>0</DisableDebug>
    <MiscSelect>0</MiscSelect>
    <MiscMask>0xFFFFFFFF</MiscMask>
</EnclaveConfiguration>
tcs_num 1, tcs_max_num 1, tcs_min_pool 1
The required memory is 2019328B.
Succeed.
SIGN =>  libenclave2.so
GEN  =>  Enclave3/Enclave3_t.c
CC   <=  Enclave3/Enclave3_t.c
CXX  <=  Enclave3/Enclave3.cpp
CXX  <=  Enclave3/Utility_E3.cpp
LINK =>  Enclave3.so
<EnclaveConfiguration>
    <ProdID>0</ProdID>
    <ISVSVN>0</ISVSVN>
    <StackMaxSize>0x40000</StackMaxSize>
    <HeapMaxSize>0x100000</HeapMaxSize>
    <TCSNum>1</TCSNum>
    <TCSPolicy>1</TCSPolicy>
    <!-- Recommend changing 'DisableDebug' to 1 to make the enclave undebuggable for enclave release -->
    <DisableDebug>0</DisableDebug>
    <MiscSelect>0</MiscSelect>
    <MiscMask>0xFFFFFFFF</MiscMask>
</EnclaveConfiguration>
tcs_num 1, tcs_max_num 1, tcs_min_pool 1
The required memory is 2019328B.
Succeed.
SIGN =>  libenclave3.so
GEN  =>  Enclave1/Enclave1_u.c
CC   <=  Enclave1/Enclave1_u.c
GEN  =>  Enclave2/Enclave2_u.c
CC   <=  Enclave2/Enclave2_u.c
GEN  =>  Enclave3/Enclave3_u.c
CC   <=  Enclave3/Enclave3_u.c
CXX  <=  App/App.cpp
LINK =>  app
The project has been built in debug simulation mode.
```

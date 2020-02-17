# Installing Intel SGX Driver
https://github.com/intel/linux-sgx-driver

I have installed the driver then the psw and lastly the sdk. Follow the documents provided. 

I downloaded the SDK from
* https://download.01.org/intel-sgx/sgx-linux/2.8/distro/ubuntu18.04-server/
* https://software.intel.com/en-us/sgx/sdk

```
➜  repos git clone https://github.com/intel/linux-sgx-driver.git
Cloning into 'linux-sgx-driver'...
remote: Enumerating objects: 28, done.
remote: Counting objects: 100% (28/28), done.
remote: Compressing objects: 100% (21/21), done.
remote: Total 446 (delta 11), reused 19 (delta 7), pack-reused 418
Receiving objects: 100% (446/446), 265.23 KiB | 4.08 MiB/s, done.
Resolving deltas: 100% (247/247), done.
➜  repos cd linux-sgx-driver 
➜  linux-sgx-driver git:(master) clear

➜  linux-sgx-driver git:(master) lsa
total 172K
drwxr-xr-x 4 spalacio spalacio 4.0K Feb 13 11:36 .
drwxr-xr-x 6 spalacio spalacio 4.0K Feb 13 11:36 ..
drwxr-xr-x 8 spalacio spalacio 4.0K Feb 13 11:36 .git
-rw-r--r-- 1 spalacio spalacio   56 Feb 13 11:36 .gitignore
drwxr-xr-x 2 spalacio spalacio 4.0K Feb 13 11:36 inker2ext
-rw-r--r-- 1 spalacio spalacio 2.4K Feb 13 11:36 License.txt
-rw-r--r-- 1 spalacio spalacio  540 Feb 13 11:36 Makefile
-rw-r--r-- 1 spalacio spalacio 4.8K Feb 13 11:36 README.md
-rw-r--r-- 1 spalacio spalacio 6.9K Feb 13 11:36 sgx_arch.h
-rw-r--r-- 1 spalacio spalacio 5.9K Feb 13 11:36 sgx_asm.h
-rw-r--r-- 1 spalacio spalacio  13K Feb 13 11:36 sgx_encl2.c
-rw-r--r-- 1 spalacio spalacio  24K Feb 13 11:36 sgx_encl.c
-rw-r--r-- 1 spalacio spalacio 8.8K Feb 13 11:36 sgx.h
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_ioctl.c
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_main.c
-rw-r--r-- 1 spalacio spalacio  15K Feb 13 11:36 sgx_page_cache.c
-rw-r--r-- 1 spalacio spalacio 5.3K Feb 13 11:36 sgx_user.h
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_util.c
-rw-r--r-- 1 spalacio spalacio 7.2K Feb 13 11:36 sgx_vma.c
➜  linux-sgx-driver git:(master) make
make -C /lib/modules/5.3.0-28-generic/build M=/home/spalacio/repos/linux-sgx-driver modules
make[1]: Entering directory '/usr/src/linux-headers-5.3.0-28-generic'
  CC [M]  /home/spalacio/repos/linux-sgx-driver/sgx_main.o
  CC [M]  /home/spalacio/repos/linux-sgx-driver/sgx_page_cache.o
  CC [M]  /home/spalacio/repos/linux-sgx-driver/sgx_ioctl.o
  CC [M]  /home/spalacio/repos/linux-sgx-driver/sgx_vma.o
  CC [M]  /home/spalacio/repos/linux-sgx-driver/sgx_util.o
  CC [M]  /home/spalacio/repos/linux-sgx-driver/sgx_encl.o
  CC [M]  /home/spalacio/repos/linux-sgx-driver/sgx_encl2.o
  LD [M]  /home/spalacio/repos/linux-sgx-driver/isgx.o
  Building modules, stage 2.
  MODPOST 1 modules
  CC      /home/spalacio/repos/linux-sgx-driver/isgx.mod.o
  LD [M]  /home/spalacio/repos/linux-sgx-driver/isgx.ko
make[1]: Leaving directory '/usr/src/linux-headers-5.3.0-28-generic'
➜  linux-sgx-driver git:(master) ✗ lsa
total 824K
drwxr-xr-x 4 spalacio spalacio 4.0K Feb 13 11:36 .
drwxr-xr-x 6 spalacio spalacio 4.0K Feb 13 11:36 ..
drwxr-xr-x 8 spalacio spalacio 4.0K Feb 13 11:36 .git
-rw-r--r-- 1 spalacio spalacio   56 Feb 13 11:36 .gitignore
drwxr-xr-x 2 spalacio spalacio 4.0K Feb 13 11:36 inker2ext
-rw-r--r-- 1 spalacio spalacio  77K Feb 13 11:36 isgx.ko
-rw-r--r-- 1 spalacio spalacio  294 Feb 13 11:36 .isgx.ko.cmd
-rw-r--r-- 1 spalacio spalacio  351 Feb 13 11:36 isgx.mod
-rw-r--r-- 1 spalacio spalacio  679 Feb 13 11:36 isgx.mod.c
-rw-r--r-- 1 spalacio spalacio  470 Feb 13 11:36 .isgx.mod.cmd
-rw-r--r-- 1 spalacio spalacio 2.9K Feb 13 11:36 isgx.mod.o
-rw-r--r-- 1 spalacio spalacio  31K Feb 13 11:36 .isgx.mod.o.cmd
-rw-r--r-- 1 spalacio spalacio  77K Feb 13 11:36 isgx.o
-rw-r--r-- 1 spalacio spalacio  500 Feb 13 11:36 .isgx.o.cmd
-rw-r--r-- 1 spalacio spalacio 2.4K Feb 13 11:36 License.txt
-rw-r--r-- 1 spalacio spalacio  540 Feb 13 11:36 Makefile
-rw-r--r-- 1 spalacio spalacio   46 Feb 13 11:36 modules.order
-rw-r--r-- 1 spalacio spalacio    0 Feb 13 11:36 Module.symvers
-rw-r--r-- 1 spalacio spalacio 4.8K Feb 13 11:36 README.md
-rw-r--r-- 1 spalacio spalacio 6.9K Feb 13 11:36 sgx_arch.h
-rw-r--r-- 1 spalacio spalacio 5.9K Feb 13 11:36 sgx_asm.h
-rw-r--r-- 1 spalacio spalacio  13K Feb 13 11:36 sgx_encl2.c
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_encl2.o
-rw-r--r-- 1 spalacio spalacio  38K Feb 13 11:36 .sgx_encl2.o.cmd
-rw-r--r-- 1 spalacio spalacio  24K Feb 13 11:36 sgx_encl.c
-rw-r--r-- 1 spalacio spalacio  25K Feb 13 11:36 sgx_encl.o
-rw-r--r-- 1 spalacio spalacio  45K Feb 13 11:36 .sgx_encl.o.cmd
-rw-r--r-- 1 spalacio spalacio 8.8K Feb 13 11:36 sgx.h
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_ioctl.c
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_ioctl.o
-rw-r--r-- 1 spalacio spalacio  45K Feb 13 11:36 .sgx_ioctl.o.cmd
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_main.c
-rw-r--r-- 1 spalacio spalacio  12K Feb 13 11:36 sgx_main.o
-rw-r--r-- 1 spalacio spalacio  49K Feb 13 11:36 .sgx_main.o.cmd
-rw-r--r-- 1 spalacio spalacio  15K Feb 13 11:36 sgx_page_cache.c
-rw-r--r-- 1 spalacio spalacio  16K Feb 13 11:36 sgx_page_cache.o
-rw-r--r-- 1 spalacio spalacio  39K Feb 13 11:36 .sgx_page_cache.o.cmd
-rw-r--r-- 1 spalacio spalacio 5.3K Feb 13 11:36 sgx_user.h
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_util.c
-rw-r--r-- 1 spalacio spalacio  14K Feb 13 11:36 sgx_util.o
-rw-r--r-- 1 spalacio spalacio  45K Feb 13 11:36 .sgx_util.o.cmd
-rw-r--r-- 1 spalacio spalacio 7.2K Feb 13 11:36 sgx_vma.c
-rw-r--r-- 1 spalacio spalacio 9.0K Feb 13 11:36 sgx_vma.o
-rw-r--r-- 1 spalacio spalacio  45K Feb 13 11:36 .sgx_vma.o.cmd
➜  linux-sgx-driver git:(master) ✗ sudo mkdir -p "/lib/modules/"`uname -r`"/kernel/drivers/intel/sgx"
➜  linux-sgx-driver git:(master) ✗ sudo cp isgx.ko "/lib/modules/"`uname -r`"/kernel/drivers/intel/sgx"
➜  linux-sgx-driver git:(master) ✗ sudo sh -c "cat /etc/modules | grep -Fxq isgx || echo isgx >> /etc/modules"
➜  linux-sgx-driver git:(master) ✗ sudo /sbin/depmod
➜  linux-sgx-driver git:(master) ✗ sudo /sbin/modprobe isgx
➜  linux-sgx-driver git:(master) ✗ lsmod | grep sgx
isgx                   53248  0
➜  linux-sgx-driver git:(master) ✗ 

```

## Installing PSW and SDK
Following this:
https://github.com/intel/linux-sgx

I need to install driver first, the PSW, then SDK. Follow [this](https://kami.app/xWs2MlPI2gmG) document too.


```
➜  linux-sgx-driver git:(master) ✗ sudo apt-get install build-essential ocaml ocamlbuild automake autoconf libtool wget python libssl-dev git
Reading package lists... Done
Building dependency tree       
Reading state information... Done
autoconf is already the newest version (2.69-11).
build-essential is already the newest version (12.4ubuntu1).
build-essential set to manually installed.
libtool is already the newest version (2.4.6-2).
python is already the newest version (2.7.15~rc1-1).
python set to manually installed.
git is already the newest version (1:2.17.1-1ubuntu0.5).
libssl-dev is already the newest version (1.1.1-1ubuntu2.1~18.04.5).
wget is already the newest version (1.19.4-1ubuntu2.2).
wget set to manually installed.
The following packages were automatically installed and are no longer required:
  gconf-service gconf-service-backend gconf2 gconf2-common gir1.2-geocodeglib-1.0 libappindicator1 libgconf-2-4 libindicator7 ubuntu-web-launchers
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  camlp4 ledit libcamlp4-ocaml-dev libfindlib-ocaml libfindlib-ocaml-dev ocaml-base ocaml-base-nox ocaml-compiler-libs ocaml-findlib ocaml-interp ocaml-nox
Suggested packages:
  autoconf-doc gnu-standards ocaml-doc tuareg-mode | ocaml-mode
The following NEW packages will be installed:
  automake camlp4 ledit libcamlp4-ocaml-dev libfindlib-ocaml libfindlib-ocaml-dev ocaml ocaml-base ocaml-base-nox ocaml-compiler-libs ocaml-findlib ocaml-interp
  ocaml-nox ocamlbuild
0 upgraded, 14 newly installed, 0 to remove and 3 not upgraded.
Need to get 73.5 MB of archives.
After this operation, 396 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 automake all 1:1.15.1-3ubuntu2 [509 kB]
Get:2 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-base-nox amd64 4.05.0-10ubuntu1 [544 kB]
Get:3 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-compiler-libs amd64 4.05.0-10ubuntu1 [18.9 MB]
Get:4 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-interp amd64 4.05.0-10ubuntu1 [3,466 kB]
Get:5 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-nox amd64 4.05.0-10ubuntu1 [27.5 MB]
Get:6 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 libcamlp4-ocaml-dev amd64 4.05+1-2 [16.2 MB]
Get:7 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 camlp4 amd64 4.05+1-2 [4,896 kB]
Get:8 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ledit all 2.03-6 [44.9 kB]
Get:9 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 libfindlib-ocaml amd64 1.7.3-2 [160 kB]
Get:10 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 libfindlib-ocaml-dev amd64 1.7.3-2 [141 kB]
Get:11 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-base amd64 4.05.0-10ubuntu1 [44.9 kB]
Get:12 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml amd64 4.05.0-10ubuntu1 [45.6 kB]
Get:13 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocaml-findlib amd64 1.7.3-2 [366 kB]
Get:14 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 ocamlbuild amd64 0.11.0-3build1 [717 kB]
Fetched 73.5 MB in 6s (12.3 MB/s)    
Selecting previously unselected package automake.
(Reading database ... 181389 files and directories currently installed.)
Preparing to unpack .../00-automake_1%3a1.15.1-3ubuntu2_all.deb ...
Unpacking automake (1:1.15.1-3ubuntu2) ...
Selecting previously unselected package ocaml-base-nox.
Preparing to unpack .../01-ocaml-base-nox_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml-base-nox (4.05.0-10ubuntu1) ...
Selecting previously unselected package ocaml-compiler-libs.
Preparing to unpack .../02-ocaml-compiler-libs_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml-compiler-libs (4.05.0-10ubuntu1) ...
Selecting previously unselected package ocaml-interp.
Preparing to unpack .../03-ocaml-interp_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml-interp (4.05.0-10ubuntu1) ...
Selecting previously unselected package ocaml-nox.
Preparing to unpack .../04-ocaml-nox_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml-nox (4.05.0-10ubuntu1) ...
Selecting previously unselected package libcamlp4-ocaml-dev.
Preparing to unpack .../05-libcamlp4-ocaml-dev_4.05+1-2_amd64.deb ...
Unpacking libcamlp4-ocaml-dev (4.05+1-2) ...
Selecting previously unselected package camlp4.
Preparing to unpack .../06-camlp4_4.05+1-2_amd64.deb ...
Unpacking camlp4 (4.05+1-2) ...
Selecting previously unselected package ledit.
Preparing to unpack .../07-ledit_2.03-6_all.deb ...
Unpacking ledit (2.03-6) ...
Selecting previously unselected package libfindlib-ocaml.
Preparing to unpack .../08-libfindlib-ocaml_1.7.3-2_amd64.deb ...
Unpacking libfindlib-ocaml (1.7.3-2) ...
Selecting previously unselected package libfindlib-ocaml-dev.
Preparing to unpack .../09-libfindlib-ocaml-dev_1.7.3-2_amd64.deb ...
Unpacking libfindlib-ocaml-dev (1.7.3-2) ...
Selecting previously unselected package ocaml-base.
Preparing to unpack .../10-ocaml-base_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml-base (4.05.0-10ubuntu1) ...
Selecting previously unselected package ocaml.
Preparing to unpack .../11-ocaml_4.05.0-10ubuntu1_amd64.deb ...
Unpacking ocaml (4.05.0-10ubuntu1) ...
Selecting previously unselected package ocaml-findlib.
Preparing to unpack .../12-ocaml-findlib_1.7.3-2_amd64.deb ...
Unpacking ocaml-findlib (1.7.3-2) ...
Selecting previously unselected package ocamlbuild.
Preparing to unpack .../13-ocamlbuild_0.11.0-3build1_amd64.deb ...
Unpacking ocamlbuild (0.11.0-3build1) ...
Setting up ocaml-base-nox (4.05.0-10ubuntu1) ...
Setting up ocaml-base (4.05.0-10ubuntu1) ...
Setting up automake (1:1.15.1-3ubuntu2) ...
update-alternatives: using /usr/bin/automake-1.15 to provide /usr/bin/automake (automake) in auto mode
Setting up ocamlbuild (0.11.0-3build1) ...
Setting up libfindlib-ocaml (1.7.3-2) ...
Setting up ocaml-findlib (1.7.3-2) ...
Setting up ledit (2.03-6) ...
update-alternatives: using /usr/bin/ledit to provide /usr/bin/readline-editor (readline-editor) in auto mode
Setting up ocaml-compiler-libs (4.05.0-10ubuntu1) ...
Setting up ocaml-interp (4.05.0-10ubuntu1) ...
Setting up ocaml-nox (4.05.0-10ubuntu1) ...
Setting up libcamlp4-ocaml-dev (4.05+1-2) ...
Setting up ocaml (4.05.0-10ubuntu1) ...
Setting up camlp4 (4.05+1-2) ...
Setting up libfindlib-ocaml-dev (1.7.3-2) ...
Processing triggers for mime-support (3.60ubuntu1) ...
Processing triggers for desktop-file-utils (0.23-1ubuntu3.18.04.2) ...
Processing triggers for install-info (6.5.0.dfsg.1-2) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for gnome-menus (3.13.3-11ubuntu1.1) ...
➜  linux-sgx-driver git:(master) ✗ sudo yum update binutils
sudo: yum: command not found
➜  linux-sgx-driver git:(master) ✗ sudo apt-get install libssl-dev libcurl4-openssl-dev protobuf-compiler libprotobuf-dev debhelper cmake reprepro
Reading package lists... Done
Building dependency tree       
Reading state information... Done
libcurl4-openssl-dev is already the newest version (7.58.0-2ubuntu3.8).
libssl-dev is already the newest version (1.1.1-1ubuntu2.1~18.04.5).
The following packages were automatically installed and are no longer required:
  gconf-service gconf-service-backend gconf2 gconf2-common gir1.2-geocodeglib-1.0 libappindicator1 libgconf-2-4 libindicator7 ubuntu-web-launchers
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  autopoint cmake-data dh-autoreconf dh-strip-nondeterminism libarchive-cpio-perl libfile-stripnondeterminism-perl libjsoncpp1 libmail-sendmail-perl
  libprotobuf-lite10 libprotoc10 librhash0 libsys-hostname-long-perl libuv1 po-debconf zlib1g-dev
Suggested packages:
  cmake-doc dh-make dwz libmail-box-perl inoticoming lzip
The following NEW packages will be installed:
  autopoint cmake cmake-data debhelper dh-autoreconf dh-strip-nondeterminism libarchive-cpio-perl libfile-stripnondeterminism-perl libjsoncpp1
  libmail-sendmail-perl libprotobuf-dev libprotobuf-lite10 libprotoc10 librhash0 libsys-hostname-long-perl libuv1 po-debconf protobuf-compiler reprepro zlib1g-dev
0 upgraded, 20 newly installed, 0 to remove and 3 not upgraded.
Need to get 8,582 kB of archives.
After this operation, 40.2 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us.archive.ubuntu.com/ubuntu bionic-updates/main amd64 autopoint all 0.19.8.1-6ubuntu0.3 [426 kB]
Get:2 http://us.archive.ubuntu.com/ubuntu bionic-updates/main amd64 cmake-data all 3.10.2-1ubuntu2.18.04.1 [1,332 kB]
Get:3 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libjsoncpp1 amd64 1.7.4-3 [73.6 kB]
Get:4 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 librhash0 amd64 1.3.6-2 [78.1 kB]
Get:5 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libuv1 amd64 1.18.0-3 [64.4 kB]
Get:6 http://us.archive.ubuntu.com/ubuntu bionic-updates/main amd64 cmake amd64 3.10.2-1ubuntu2.18.04.1 [3,152 kB]
Get:7 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 dh-autoreconf all 17 [15.8 kB]
Get:8 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libfile-stripnondeterminism-perl all 0.040-1.1~build1 [13.8 kB]
Get:9 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 dh-strip-nondeterminism all 0.040-1.1~build1 [5,208 B]
Get:10 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 po-debconf all 1.0.20 [232 kB]
Get:11 http://us.archive.ubuntu.com/ubuntu bionic-updates/main amd64 debhelper all 11.1.6ubuntu2 [902 kB]
Get:12 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libarchive-cpio-perl all 0.10-1 [9,644 B]
Get:13 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libsys-hostname-long-perl all 1.5-1 [11.7 kB]
Get:14 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libmail-sendmail-perl all 0.80-1 [22.6 kB]
Get:15 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libprotobuf-lite10 amd64 3.0.0-9.1ubuntu1 [97.7 kB]
Get:16 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libprotoc10 amd64 3.0.0-9.1ubuntu1 [566 kB]
Get:17 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 zlib1g-dev amd64 1:1.2.11.dfsg-0ubuntu2 [176 kB]
Get:18 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libprotobuf-dev amd64 3.0.0-9.1ubuntu1 [959 kB]
Get:19 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 protobuf-compiler amd64 3.0.0-9.1ubuntu1 [24.5 kB]
Get:20 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 reprepro amd64 5.1.1-1 [421 kB]
Fetched 8,582 kB in 1s (7,827 kB/s)
Selecting previously unselected package autopoint.
(Reading database ... 183992 files and directories currently installed.)
Preparing to unpack .../00-autopoint_0.19.8.1-6ubuntu0.3_all.deb ...
Unpacking autopoint (0.19.8.1-6ubuntu0.3) ...
Selecting previously unselected package cmake-data.
Preparing to unpack .../01-cmake-data_3.10.2-1ubuntu2.18.04.1_all.deb ...
Unpacking cmake-data (3.10.2-1ubuntu2.18.04.1) ...
Selecting previously unselected package libjsoncpp1:amd64.
Preparing to unpack .../02-libjsoncpp1_1.7.4-3_amd64.deb ...
Unpacking libjsoncpp1:amd64 (1.7.4-3) ...
Selecting previously unselected package librhash0:amd64.
Preparing to unpack .../03-librhash0_1.3.6-2_amd64.deb ...
Unpacking librhash0:amd64 (1.3.6-2) ...
Selecting previously unselected package libuv1:amd64.
Preparing to unpack .../04-libuv1_1.18.0-3_amd64.deb ...
Unpacking libuv1:amd64 (1.18.0-3) ...
Selecting previously unselected package cmake.
Preparing to unpack .../05-cmake_3.10.2-1ubuntu2.18.04.1_amd64.deb ...
Unpacking cmake (3.10.2-1ubuntu2.18.04.1) ...
Selecting previously unselected package dh-autoreconf.
Preparing to unpack .../06-dh-autoreconf_17_all.deb ...
Unpacking dh-autoreconf (17) ...
Selecting previously unselected package libfile-stripnondeterminism-perl.
Preparing to unpack .../07-libfile-stripnondeterminism-perl_0.040-1.1~build1_all.deb ...
Unpacking libfile-stripnondeterminism-perl (0.040-1.1~build1) ...
Selecting previously unselected package dh-strip-nondeterminism.
Preparing to unpack .../08-dh-strip-nondeterminism_0.040-1.1~build1_all.deb ...
Unpacking dh-strip-nondeterminism (0.040-1.1~build1) ...
Selecting previously unselected package po-debconf.
Preparing to unpack .../09-po-debconf_1.0.20_all.deb ...
Unpacking po-debconf (1.0.20) ...
Selecting previously unselected package debhelper.
Preparing to unpack .../10-debhelper_11.1.6ubuntu2_all.deb ...
Unpacking debhelper (11.1.6ubuntu2) ...
Selecting previously unselected package libarchive-cpio-perl.
Preparing to unpack .../11-libarchive-cpio-perl_0.10-1_all.deb ...
Unpacking libarchive-cpio-perl (0.10-1) ...
Selecting previously unselected package libsys-hostname-long-perl.
Preparing to unpack .../12-libsys-hostname-long-perl_1.5-1_all.deb ...
Unpacking libsys-hostname-long-perl (1.5-1) ...
Selecting previously unselected package libmail-sendmail-perl.
Preparing to unpack .../13-libmail-sendmail-perl_0.80-1_all.deb ...
Unpacking libmail-sendmail-perl (0.80-1) ...
Selecting previously unselected package libprotobuf-lite10:amd64.
Preparing to unpack .../14-libprotobuf-lite10_3.0.0-9.1ubuntu1_amd64.deb ...
Unpacking libprotobuf-lite10:amd64 (3.0.0-9.1ubuntu1) ...
Selecting previously unselected package libprotoc10:amd64.
Preparing to unpack .../15-libprotoc10_3.0.0-9.1ubuntu1_amd64.deb ...
Unpacking libprotoc10:amd64 (3.0.0-9.1ubuntu1) ...
Selecting previously unselected package zlib1g-dev:amd64.
Preparing to unpack .../16-zlib1g-dev_1%3a1.2.11.dfsg-0ubuntu2_amd64.deb ...
Unpacking zlib1g-dev:amd64 (1:1.2.11.dfsg-0ubuntu2) ...
Selecting previously unselected package libprotobuf-dev:amd64.
Preparing to unpack .../17-libprotobuf-dev_3.0.0-9.1ubuntu1_amd64.deb ...
Unpacking libprotobuf-dev:amd64 (3.0.0-9.1ubuntu1) ...
Selecting previously unselected package protobuf-compiler.
Preparing to unpack .../18-protobuf-compiler_3.0.0-9.1ubuntu1_amd64.deb ...
Unpacking protobuf-compiler (3.0.0-9.1ubuntu1) ...
Selecting previously unselected package reprepro.
Preparing to unpack .../19-reprepro_5.1.1-1_amd64.deb ...
Unpacking reprepro (5.1.1-1) ...
Setting up po-debconf (1.0.20) ...
Setting up libuv1:amd64 (1.18.0-3) ...
Setting up libarchive-cpio-perl (0.10-1) ...
Setting up cmake-data (3.10.2-1ubuntu2.18.04.1) ...
Setting up reprepro (5.1.1-1) ...
Setting up librhash0:amd64 (1.3.6-2) ...
Setting up libsys-hostname-long-perl (1.5-1) ...
Setting up libmail-sendmail-perl (0.80-1) ...
Setting up libprotobuf-lite10:amd64 (3.0.0-9.1ubuntu1) ...
Setting up libprotoc10:amd64 (3.0.0-9.1ubuntu1) ...
Setting up autopoint (0.19.8.1-6ubuntu0.3) ...
Setting up zlib1g-dev:amd64 (1:1.2.11.dfsg-0ubuntu2) ...
Setting up libfile-stripnondeterminism-perl (0.040-1.1~build1) ...
Setting up libjsoncpp1:amd64 (1.7.4-3) ...
Setting up protobuf-compiler (3.0.0-9.1ubuntu1) ...
Setting up libprotobuf-dev:amd64 (3.0.0-9.1ubuntu1) ...
Setting up cmake (3.10.2-1ubuntu2.18.04.1) ...
Setting up debhelper (11.1.6ubuntu2) ...
Setting up dh-autoreconf (17) ...
Setting up dh-strip-nondeterminism (0.040-1.1~build1) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
➜  linux-sgx-driver git:(master) ✗ pwd
/home/spalacio/repos/linux-sgx-driver
➜  linux-sgx-driver git:(master) ✗ echo 'deb [arch=amd64] https://-download.01.org/intel-sgx/sgx_repo/ubuntubionic main' | sudo tee /etc/apt/sources.list.d/intel-sgx.l-ist
deb [arch=amd64] https://-download.01.org/intel-sgx/sgx_repo/ubuntubionic main
➜  linux-sgx-driver git:(master) ✗ wget -qO - https://download.01.org/intel-sgx/sgx_repo/ubuntu/intel-sgx-deb.key\| sudo apt-key add -
➜  linux-sgx-driver git:(master) ✗ sudo apt-get install libsgx-launch libsgx-urts
Reading package lists... Done
Building dependency tree       
Reading state information... Done
libsgx-urts is already the newest version (2.8.100.3-bionic1).
The following packages were automatically installed and are no longer required:
  gconf-service gconf-service-backend gconf2 gconf2-common gir1.2-geocodeglib-1.0 libappindicator1 libgconf-2-4 libindicator7 ubuntu-web-launchers
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  libsgx-ae-le libsgx-aesm-launch-plugin sgx-aesm-service
The following NEW packages will be installed:
  libsgx-ae-le libsgx-aesm-launch-plugin libsgx-launch sgx-aesm-service
0 upgraded, 4 newly installed, 0 to remove and 3 not upgraded.
Need to get 826 kB of archives.
After this operation, 3,369 kB of additional disk space will be used.
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
Do you want to continue? [Y/n] y
Get:1 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic/main amd64 libsgx-ae-le amd64 2.8.100.3-bionic1 [201 kB]
Get:2 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic/main amd64 sgx-aesm-service amd64 2.8.100.3-bionic1 [518 kB]
Get:3 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic/main amd64 libsgx-aesm-launch-plugin amd64 2.8.100.3-bionic1 [39.1 kB]
Get:4 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic/main amd64 libsgx-launch amd64 2.8.100.3-bionic1 [67.1 kB]
Fetched 826 kB in 1s (904 kB/s)          
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
Selecting previously unselected package libsgx-ae-le.
(Reading database ... 187201 files and directories currently installed.)
Preparing to unpack .../libsgx-ae-le_2.8.100.3-bionic1_amd64.deb ...
Unpacking libsgx-ae-le (2.8.100.3-bionic1) ...
Selecting previously unselected package sgx-aesm-service.
Preparing to unpack .../sgx-aesm-service_2.8.100.3-bionic1_amd64.deb ...
Unpacking sgx-aesm-service (2.8.100.3-bionic1) ...
Selecting previously unselected package libsgx-aesm-launch-plugin.
Preparing to unpack .../libsgx-aesm-launch-plugin_2.8.100.3-bionic1_amd64.deb ...
Unpacking libsgx-aesm-launch-plugin (2.8.100.3-bionic1) ...
Selecting previously unselected package libsgx-launch.
Preparing to unpack .../libsgx-launch_2.8.100.3-bionic1_amd64.deb ...
Unpacking libsgx-launch (2.8.100.3-bionic1) ...
Setting up libsgx-launch (2.8.100.3-bionic1) ...
Setting up libsgx-ae-le (2.8.100.3-bionic1) ...
Setting up sgx-aesm-service (2.8.100.3-bionic1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/aesmd.service → /lib/systemd/system/aesmd.service.
Setting up libsgx-aesm-launch-plugin (2.8.100.3-bionic1) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
➜  linux-sgx-driver git:(master) ✗ sudo apt-get install libsgx-epid libsgx-urts  
Reading package lists... Done
Building dependency tree       
Reading state information... Done
libsgx-urts is already the newest version (2.8.100.3-bionic1).
The following packages were automatically installed and are no longer required:
  gconf-service gconf-service-backend gconf2 gconf2-common gir1.2-geocodeglib-1.0 libappindicator1 libgconf-2-4 libindicator7 ubuntu-web-launchers
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  libsgx-ae-epid libsgx-aesm-epid-plugin libsgx-aesm-pce-plugin
The following NEW packages will be installed:
  libsgx-ae-epid libsgx-aesm-epid-plugin libsgx-aesm-pce-plugin libsgx-epid
0 upgraded, 4 newly installed, 0 to remove and 3 not upgraded.
Need to get 586 kB of archives.
After this operation, 3,724 kB of additional disk space will be used.
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
Do you want to continue? [Y/n] y
Get:1 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic/main amd64 libsgx-ae-epid amd64 2.8.100.3-bionic1 [426 kB]
Get:2 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic/main amd64 libsgx-aesm-pce-plugin amd64 2.8.100.3-bionic1 [32.1 kB]
Get:3 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic/main amd64 libsgx-aesm-epid-plugin amd64 2.8.100.3-bionic1 [59.0 kB]
Get:4 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic/main amd64 libsgx-epid amd64 2.8.100.3-bionic1 [68.5 kB]
Fetched 586 kB in 1s (990 kB/s)       
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
Selecting previously unselected package libsgx-ae-epid.
(Reading database ... 187239 files and directories currently installed.)
Preparing to unpack .../libsgx-ae-epid_2.8.100.3-bionic1_amd64.deb ...
Unpacking libsgx-ae-epid (2.8.100.3-bionic1) ...
Selecting previously unselected package libsgx-aesm-pce-plugin.
Preparing to unpack .../libsgx-aesm-pce-plugin_2.8.100.3-bionic1_amd64.deb ...
Unpacking libsgx-aesm-pce-plugin (2.8.100.3-bionic1) ...
Selecting previously unselected package libsgx-aesm-epid-plugin.
Preparing to unpack .../libsgx-aesm-epid-plugin_2.8.100.3-bionic1_amd64.deb ...
Unpacking libsgx-aesm-epid-plugin (2.8.100.3-bionic1) ...
Selecting previously unselected package libsgx-epid.
Preparing to unpack .../libsgx-epid_2.8.100.3-bionic1_amd64.deb ...
Unpacking libsgx-epid (2.8.100.3-bionic1) ...
Setting up libsgx-epid (2.8.100.3-bionic1) ...
Setting up libsgx-aesm-pce-plugin (2.8.100.3-bionic1) ...
Setting up libsgx-ae-epid (2.8.100.3-bionic1) ...
Setting up libsgx-aesm-epid-plugin (2.8.100.3-bionic1) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
➜  linux-sgx-driver git:(master) ✗ sudo apt-get install libsgx-quote-ex libsgx-urts
Reading package lists... Done
Building dependency tree       
Reading state information... Done
libsgx-urts is already the newest version (2.8.100.3-bionic1).
The following packages were automatically installed and are no longer required:
  gconf-service gconf-service-backend gconf2 gconf2-common gir1.2-geocodeglib-1.0 libappindicator1 libgconf-2-4 libindicator7 ubuntu-web-launchers
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  libsgx-aesm-ecdsa-plugin libsgx-aesm-quote-ex-plugin
The following NEW packages will be installed:
  libsgx-aesm-ecdsa-plugin libsgx-aesm-quote-ex-plugin libsgx-quote-ex
0 upgraded, 3 newly installed, 0 to remove and 3 not upgraded.
Need to get 151 kB of archives.
After this operation, 683 kB of additional disk space will be used.
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
Do you want to continue? [Y/n] y
Get:1 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic/main amd64 libsgx-aesm-ecdsa-plugin amd64 2.8.100.3-bionic1 [41.7 kB]
Get:2 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic/main amd64 libsgx-aesm-quote-ex-plugin amd64 2.8.100.3-bionic1 [40.9 kB]
Get:3 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic/main amd64 libsgx-quote-ex amd64 2.8.100.3-bionic1 [68.0 kB]
Fetched 151 kB in 0s (374 kB/s)            
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
Selecting previously unselected package libsgx-aesm-ecdsa-plugin.
(Reading database ... 187258 files and directories currently installed.)
Preparing to unpack .../libsgx-aesm-ecdsa-plugin_2.8.100.3-bionic1_amd64.deb ...
Unpacking libsgx-aesm-ecdsa-plugin (2.8.100.3-bionic1) ...
Selecting previously unselected package libsgx-aesm-quote-ex-plugin.
Preparing to unpack .../libsgx-aesm-quote-ex-plugin_2.8.100.3-bionic1_amd64.deb ...
Unpacking libsgx-aesm-quote-ex-plugin (2.8.100.3-bionic1) ...
Selecting previously unselected package libsgx-quote-ex.
Preparing to unpack .../libsgx-quote-ex_2.8.100.3-bionic1_amd64.deb ...
Unpacking libsgx-quote-ex (2.8.100.3-bionic1) ...
Setting up libsgx-aesm-ecdsa-plugin (2.8.100.3-bionic1) ...
Setting up libsgx-quote-ex (2.8.100.3-bionic1) ...
Setting up libsgx-aesm-quote-ex-plugin (2.8.100.3-bionic1) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
➜  linux-sgx-driver git:(master) ✗ lsa /opt/intel 
total 16K
drwxr-xr-x 4 root root 4.0K Feb 13 11:55 .
drwxr-xr-x 6 root root 4.0K Feb 12 19:25 ..
drwxr-xr-x 3 root root 4.0K Feb 13 11:55 sgx-aesm-service
drwxr-xr-x 2 root root 4.0K Feb  7 01:18 sgxdriver
➜  linux-sgx-driver git:(master) ✗ lsa /var/opt 
total 12K
drwxr-xr-x  3 root  root  4.0K Feb 13 11:55 .
drwxr-xr-x 14 root  root  4.0K Aug  5  2019 ..
drwxr-x---  3 aesmd aesmd 4.0K Feb 13 11:55 aesmd
➜  linux-sgx-driver git:(master) ✗ pwd
/home/spalacio/repos/linux-sgx-driver
➜  linux-sgx-driver git:(master) ✗ lsa
total 7.9M
drwxr-xr-x 4 spalacio spalacio 4.0K Feb 13 11:51 .
drwxr-xr-x 6 spalacio spalacio 4.0K Feb 13 11:36 ..
drwxr-xr-x 8 spalacio spalacio 4.0K Feb 13 12:00 .git
-rw-r--r-- 1 spalacio spalacio   56 Feb 13 11:36 .gitignore
drwxr-xr-x 2 spalacio spalacio 4.0K Feb 13 11:36 inker2ext
-rw-r--r-- 1 spalacio spalacio  77K Feb 13 11:36 isgx.ko
-rw-r--r-- 1 spalacio spalacio  294 Feb 13 11:36 .isgx.ko.cmd
-rw-r--r-- 1 spalacio spalacio  351 Feb 13 11:36 isgx.mod
-rw-r--r-- 1 spalacio spalacio  679 Feb 13 11:36 isgx.mod.c
-rw-r--r-- 1 spalacio spalacio  470 Feb 13 11:36 .isgx.mod.cmd
-rw-r--r-- 1 spalacio spalacio 2.9K Feb 13 11:36 isgx.mod.o
-rw-r--r-- 1 spalacio spalacio  31K Feb 13 11:36 .isgx.mod.o.cmd
-rw-r--r-- 1 spalacio spalacio  77K Feb 13 11:36 isgx.o
-rw-r--r-- 1 spalacio spalacio  500 Feb 13 11:36 .isgx.o.cmd
-rw-r--r-- 1 spalacio spalacio 2.4K Feb 13 11:36 License.txt
-rw-r--r-- 1 spalacio spalacio  540 Feb 13 11:36 Makefile
-rw-r--r-- 1 spalacio spalacio   46 Feb 13 11:36 modules.order
-rw-r--r-- 1 spalacio spalacio    0 Feb 13 11:36 Module.symvers
-rw-r--r-- 1 spalacio spalacio 4.8K Feb 13 11:36 README.md
-rw-r--r-- 1 spalacio spalacio 6.9K Feb 13 11:36 sgx_arch.h
-rw-r--r-- 1 spalacio spalacio 5.9K Feb 13 11:36 sgx_asm.h
-rw-r--r-- 1 spalacio spalacio  13K Feb 13 11:36 sgx_encl2.c
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_encl2.o
-rw-r--r-- 1 spalacio spalacio  38K Feb 13 11:36 .sgx_encl2.o.cmd
-rw-r--r-- 1 spalacio spalacio  24K Feb 13 11:36 sgx_encl.c
-rw-r--r-- 1 spalacio spalacio  25K Feb 13 11:36 sgx_encl.o
-rw-r--r-- 1 spalacio spalacio  45K Feb 13 11:36 .sgx_encl.o.cmd
-rw-r--r-- 1 spalacio spalacio 8.8K Feb 13 11:36 sgx.h
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_ioctl.c
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_ioctl.o
-rw-r--r-- 1 spalacio spalacio  45K Feb 13 11:36 .sgx_ioctl.o.cmd
-rw-rw-r-- 1 spalacio spalacio 7.1M Feb 13 11:50 sgx_linux_x64_sdk_2.8.100.3.bin
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_main.c
-rw-r--r-- 1 spalacio spalacio  12K Feb 13 11:36 sgx_main.o
-rw-r--r-- 1 spalacio spalacio  49K Feb 13 11:36 .sgx_main.o.cmd
-rw-r--r-- 1 spalacio spalacio  15K Feb 13 11:36 sgx_page_cache.c
-rw-r--r-- 1 spalacio spalacio  16K Feb 13 11:36 sgx_page_cache.o
-rw-r--r-- 1 spalacio spalacio  39K Feb 13 11:36 .sgx_page_cache.o.cmd
-rw-r--r-- 1 spalacio spalacio 5.3K Feb 13 11:36 sgx_user.h
-rw-r--r-- 1 spalacio spalacio  11K Feb 13 11:36 sgx_util.c
-rw-r--r-- 1 spalacio spalacio  14K Feb 13 11:36 sgx_util.o
-rw-r--r-- 1 spalacio spalacio  45K Feb 13 11:36 .sgx_util.o.cmd
-rw-r--r-- 1 spalacio spalacio 7.2K Feb 13 11:36 sgx_vma.c
-rw-r--r-- 1 spalacio spalacio 9.0K Feb 13 11:36 sgx_vma.o
-rw-r--r-- 1 spalacio spalacio  45K Feb 13 11:36 .sgx_vma.o.cmd
➜  linux-sgx-driver git:(master) ✗ chmod 755 sgx_linux_x64_sdk_2.8.100.3.bin 
➜  linux-sgx-driver git:(master) ✗ ./sgx_linux_x64_sdk_2.8.100.3.bin 

Do you want to install in current directory? [yes/no] : yes
Unpacking Intel SGX SDK ... done.
Verifying the integrity of the install package ... done.
Installing Intel SGX SDK ... done.
/tmp/sgx-sdk-jJ9OkO ~/repos/linux-sgx-driver
install -d /home/spalacio/repos/linux-sgx-driver/sgxsdk
cp -r package/* /home/spalacio/repos/linux-sgx-driver/sgxsdk
install -d /home/spalacio/repos/linux-sgx-driver/sgxsdk/scripts
install scripts/* /home/spalacio/repos/linux-sgx-driver/sgxsdk/scripts
chmod +x /home/spalacio/repos/linux-sgx-driver/sgxsdk/bin/sgx-gdb
~/repos/linux-sgx-driver
uninstall.sh script generated in /home/spalacio/repos/linux-sgx-driver/sgxsdk

Installation is successful! The SDK package can be found in /home/spalacio/repos/linux-sgx-driver/sgxsdk

Please set the environment variables with below command:

source /home/spalacio/repos/linux-sgx-driver/sgxsdk/environment
➜  linux-sgx-driver git:(master) ✗ source /home/spalacio/repos/linux-sgx-driver/sgxsdk/environment
```

### checking aesm service

```
➜  linux-sgx-driver git:(master) ✗ lsmod | grep sgx  
isgx                   53248  2
➜  linux-sgx-driver git:(master) ✗ service aesmd status
● aesmd.service - Intel(R) Architectural Enclave Service Manager
   Loaded: loaded (/lib/systemd/system/aesmd.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-02-13 11:55:42 EST; 13min ago
  Process: 24950 ExecStart=/opt/intel/sgx-aesm-service/aesm/aesm_service (code=exited, status=0/SUCCESS)
  Process: 24949 ExecStartPre=/bin/chmod 0750 /var/opt/aesmd/ (code=exited, status=0/SUCCESS)
  Process: 24948 ExecStartPre=/bin/chown -R aesmd:aesmd /var/opt/aesmd/ (code=exited, status=0/SUCCESS)
  Process: 24945 ExecStartPre=/bin/chmod 0755 /var/run/aesmd/ (code=exited, status=0/SUCCESS)
  Process: 24944 ExecStartPre=/bin/chown -R aesmd:aesmd /var/run/aesmd/ (code=exited, status=0/SUCCESS)
  Process: 24943 ExecStartPre=/bin/mkdir -p /var/run/aesmd/ (code=exited, status=0/SUCCESS)
  Process: 24938 ExecStartPre=/opt/intel/sgx-aesm-service/aesm/linksgx.sh (code=exited, status=0/SUCCESS)
 Main PID: 24951 (aesm_service)
    Tasks: 4 (limit: 4915)
   CGroup: /system.slice/aesmd.service
           └─24951 /opt/intel/sgx-aesm-service/aesm/aesm_service

Feb 13 11:55:42 maverickzhn01 systemd[1]: Starting Intel(R) Architectural Enclave Service Manager...
Feb 13 11:55:42 maverickzhn01 systemd[1]: Started Intel(R) Architectural Enclave Service Manager.
Feb 13 11:55:42 maverickzhn01 aesm_service[24951]: [ADMIN]White List update requested
Feb 13 11:55:42 maverickzhn01 aesm_service[24951]: The server sock is 0x55f977fc6570
Feb 13 11:55:42 maverickzhn01 aesm_service[24951]: [ADMIN]White list update request successful for Version: 69
```

### Install Docker
Followed this document: https://phoenixnap.com/kb/how-to-install-docker-on-ubuntu-18-04
```
➜  repos sudo apt-get update
[sudo] password for spalacio: 
Hit:1 http://apt.llvm.org/bionic llvm-toolchain-bionic-7 InRelease
Ign:2 http://dl.google.com/linux/chrome/deb stable InRelease                                                                                                                                             
Hit:3 http://us.archive.ubuntu.com/ubuntu bionic InRelease                                                                                                                                                        
Hit:4 https://packages.microsoft.com/ubuntu/18.04/prod bionic InRelease                                                                                                                                           
Get:5 http://us.archive.ubuntu.com/ubuntu bionic-updates InRelease [88.7 kB]                                                                                                
Get:6 http://security.ubuntu.com/ubuntu bionic-security InRelease [88.7 kB]                                                                           
Hit:7 https://download.sublimetext.com apt/stable/ InRelease                                                                               
Get:8 http://us.archive.ubuntu.com/ubuntu bionic-backports InRelease [74.6 kB]                                                             
Hit:9 http://dl.google.com/linux/chrome/deb stable Release                                                             
Get:10 http://us.archive.ubuntu.com/ubuntu bionic-updates/main amd64 DEP-11 Metadata [294 kB]     
Get:12 http://us.archive.ubuntu.com/ubuntu bionic-updates/main DEP-11 48x48 Icons [73.8 kB]              
Get:13 http://us.archive.ubuntu.com/ubuntu bionic-updates/main DEP-11 64x64 Icons [140 kB]
Get:14 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 DEP-11 Metadata [264 kB]                
Get:15 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe DEP-11 48x48 Icons [205 kB]                        
Get:16 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe DEP-11 64x64 Icons [454 kB]                   
Get:17 http://us.archive.ubuntu.com/ubuntu bionic-updates/multiverse amd64 DEP-11 Metadata [2,464 B]             
Get:18 http://us.archive.ubuntu.com/ubuntu bionic-backports/universe amd64 DEP-11 Metadata [8,280 B]
Get:19 http://security.ubuntu.com/ubuntu bionic-security/main amd64 DEP-11 Metadata [38.5 kB]                            
Hit:20 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic InRelease                         
Get:21 http://security.ubuntu.com/ubuntu bionic-security/main DEP-11 48x48 Icons [17.6 kB]
Get:22 http://security.ubuntu.com/ubuntu bionic-security/main DEP-11 64x64 Icons [41.5 kB]
Get:23 http://security.ubuntu.com/ubuntu bionic-security/universe amd64 DEP-11 Metadata [42.1 kB]
Get:24 http://security.ubuntu.com/ubuntu bionic-security/universe DEP-11 48x48 Icons [16.4 kB]
Get:25 http://security.ubuntu.com/ubuntu bionic-security/universe DEP-11 64x64 Icons [111 kB]
Get:26 http://security.ubuntu.com/ubuntu bionic-security/multiverse amd64 DEP-11 Metadata [2,464 B]
Fetched 1,963 kB in 1s (1,602 kB/s)                                       
Reading package lists... Done
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
➜  repos sudo apt-get remove docker docker-engine docker.io
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Package 'docker-engine' is not installed, so not removed
Package 'docker' is not installed, so not removed
Package 'docker.io' is not installed, so not removed
The following packages were automatically installed and are no longer required:
  gconf-service gconf-service-backend gconf2 gconf2-common gir1.2-geocodeglib-1.0 libappindicator1 libgconf-2-4 libindicator7 ubuntu-web-launchers
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 4 not upgraded.
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
➜  repos sudo apt install docker.io
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages were automatically installed and are no longer required:
  gconf-service gconf-service-backend gconf2 gconf2-common gir1.2-geocodeglib-1.0 libappindicator1 libgconf-2-4 libindicator7 ubuntu-web-launchers
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  bridge-utils cgroupfs-mount containerd pigz runc ubuntu-fan
Suggested packages:
  aufs-tools btrfs-progs debootstrap docker-doc rinse zfs-fuse | zfsutils
The following NEW packages will be installed:
  bridge-utils cgroupfs-mount containerd docker.io pigz runc ubuntu-fan
0 upgraded, 7 newly installed, 0 to remove and 4 not upgraded.
Need to get 52.2 MB of archives.
After this operation, 257 MB of additional disk space will be used.
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
Do you want to continue? [Y/n] y
Get:1 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 pigz amd64 2.4-1 [57.4 kB]
Get:2 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 bridge-utils amd64 1.5-15ubuntu1 [30.1 kB]
Get:3 http://us.archive.ubuntu.com/ubuntu bionic/universe amd64 cgroupfs-mount all 1.4 [6,320 B]
Get:4 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 runc amd64 1.0.0~rc7+git20190403.029124da-0ubuntu1~18.04.2 [1,903 kB]
Get:5 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 containerd amd64 1.2.6-0ubuntu1~18.04.2 [19.4 MB]
Get:6 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 docker.io amd64 18.09.7-0ubuntu1~18.04.4 [30.7 MB]
Get:7 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 ubuntu-fan all 0.12.10 [34.7 kB]
Fetched 52.2 MB in 3s (15.0 MB/s)     
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
Preconfiguring packages ...
Selecting previously unselected package pigz.
(Reading database ... 187317 files and directories currently installed.)
Preparing to unpack .../0-pigz_2.4-1_amd64.deb ...
Unpacking pigz (2.4-1) ...
Selecting previously unselected package bridge-utils.
Preparing to unpack .../1-bridge-utils_1.5-15ubuntu1_amd64.deb ...
Unpacking bridge-utils (1.5-15ubuntu1) ...
Selecting previously unselected package cgroupfs-mount.
Preparing to unpack .../2-cgroupfs-mount_1.4_all.deb ...
Unpacking cgroupfs-mount (1.4) ...
Selecting previously unselected package runc.
Preparing to unpack .../3-runc_1.0.0~rc7+git20190403.029124da-0ubuntu1~18.04.2_amd64.deb ...
Unpacking runc (1.0.0~rc7+git20190403.029124da-0ubuntu1~18.04.2) ...
Selecting previously unselected package containerd.
Preparing to unpack .../4-containerd_1.2.6-0ubuntu1~18.04.2_amd64.deb ...
Unpacking containerd (1.2.6-0ubuntu1~18.04.2) ...
Selecting previously unselected package docker.io.
Preparing to unpack .../5-docker.io_18.09.7-0ubuntu1~18.04.4_amd64.deb ...
Unpacking docker.io (18.09.7-0ubuntu1~18.04.4) ...
Selecting previously unselected package ubuntu-fan.
Preparing to unpack .../6-ubuntu-fan_0.12.10_all.deb ...
Unpacking ubuntu-fan (0.12.10) ...
Setting up runc (1.0.0~rc7+git20190403.029124da-0ubuntu1~18.04.2) ...
Setting up cgroupfs-mount (1.4) ...
Setting up containerd (1.2.6-0ubuntu1~18.04.2) ...
Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /lib/systemd/system/containerd.service.
Setting up bridge-utils (1.5-15ubuntu1) ...
Setting up ubuntu-fan (0.12.10) ...
Created symlink /etc/systemd/system/multi-user.target.wants/ubuntu-fan.service → /lib/systemd/system/ubuntu-fan.service.
Setting up pigz (2.4-1) ...
Setting up docker.io (18.09.7-0ubuntu1~18.04.4) ...
Adding group `docker' (GID 127) ...
Done.
Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /lib/systemd/system/docker.socket.
Processing triggers for systemd (237-3ubuntu10.38) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for ureadahead (0.100.0-21) ...
ureadahead will be reprofiled on next reboot
➜  repos sudo systemctl start docker
➜  repos sudo systemctl enable docker
Synchronizing state of docker.service with SysV service script with /lib/systemd/systemd-sysv-install.
Executing: /lib/systemd/systemd-sysv-install enable docker
➜  repos docker --version
Docker version 18.09.7, build 2d0083d
```

### Installing Insomnia
```
 oada-srvc-docker git:(master) echo "deb https://dl.bintray.com/getinsomnia/Insomnia /" \
    | sudo tee -a /etc/apt/sources.list.d/insomnia.list
[sudo] password for spalacio: 
deb https://dl.bintray.com/getinsomnia/Insomnia /
➜  oada-srvc-docker git:(master) wget --quiet -O - https://insomnia.rest/keys/debian-public.key.asc \
    | sudo apt-key add -
OK
➜  oada-srvc-docker git:(master) sudo apt-get update
Hit:1 http://us.archive.ubuntu.com/ubuntu bionic InRelease
Ign:2 http://dl.google.com/linux/chrome/deb stable InRelease                                            
Get:3 http://us.archive.ubuntu.com/ubuntu bionic-updates InRelease [88.7 kB]                            
Get:4 http://security.ubuntu.com/ubuntu bionic-security InRelease [88.7 kB]                             
Get:5 http://us.archive.ubuntu.com/ubuntu bionic-backports InRelease [74.6 kB]                          
Hit:6 https://packages.microsoft.com/ubuntu/18.04/prod bionic InRelease                                 
Hit:7 https://download.sublimetext.com apt/stable/ InRelease                                            
Ign:8 https://dl.bintray.com/getinsomnia/Insomnia  InRelease                                            
Get:9 http://us.archive.ubuntu.com/ubuntu bionic-updates/main amd64 DEP-11 Metadata [294 kB]            
Get:10 https://dl.bintray.com/getinsomnia/Insomnia  Release [815 B]                                     
Hit:11 http://dl.google.com/linux/chrome/deb stable Release                                             
Get:12 http://us.archive.ubuntu.com/ubuntu bionic-updates/main DEP-11 48x48 Icons [73.8 kB]             
Get:13 http://us.archive.ubuntu.com/ubuntu bionic-updates/main DEP-11 64x64 Icons [140 kB]              
Get:14 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 DEP-11 Metadata [264 kB]       
Get:15 https://dl.bintray.com/getinsomnia/Insomnia  Release.gpg [821 B]                                 
Get:16 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe DEP-11 48x48 Icons [195 kB]          
Get:17 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe DEP-11 64x64 Icons [440 kB]          
Get:18 http://us.archive.ubuntu.com/ubuntu bionic-updates/multiverse amd64 DEP-11 Metadata [2,464 B]    
Get:19 http://us.archive.ubuntu.com/ubuntu bionic-backports/universe amd64 DEP-11 Metadata [8,280 B]    
Hit:21 http://apt.llvm.org/bionic llvm-toolchain-bionic-7 InRelease                                     
Get:22 https://dl.bintray.com/getinsomnia/Insomnia  Packages [3,655 B]          
Get:23 http://security.ubuntu.com/ubuntu bionic-security/main amd64 DEP-11 Metadata [38.5 kB]
Get:24 http://security.ubuntu.com/ubuntu bionic-security/main DEP-11 48x48 Icons [17.6 kB]
Get:25 http://security.ubuntu.com/ubuntu bionic-security/main DEP-11 64x64 Icons [41.5 kB]
Get:26 http://security.ubuntu.com/ubuntu bionic-security/universe amd64 DEP-11 Metadata [42.1 kB]
Get:27 http://security.ubuntu.com/ubuntu bionic-security/universe DEP-11 48x48 Icons [16.4 kB]
Get:28 http://security.ubuntu.com/ubuntu bionic-security/universe DEP-11 64x64 Icons [113 kB]
Get:29 http://security.ubuntu.com/ubuntu bionic-security/multiverse amd64 DEP-11 Metadata [2,464 B]
Hit:30 https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic InRelease                    
Fetched 1,947 kB in 1s (1,460 kB/s)
Reading package lists... Done
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
➜  oada-srvc-docker git:(master) sudo apt-get install insomnia
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages were automatically installed and are no longer required:
  gconf-service gconf-service-backend gconf2 gconf2-common gir1.2-geocodeglib-1.0 libappindicator1
  libgconf-2-4 libindicator7 ubuntu-web-launchers
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  insomnia
0 upgraded, 1 newly installed, 0 to remove and 4 not upgraded.
Need to get 45.5 MB of archives.
After this operation, 211 MB of additional disk space will be used.
Get:1 https://dl.bintray.com/getinsomnia/Insomnia  insomnia 7.1.0 [45.5 MB]
Fetched 45.5 MB in 23s (2,019 kB/s)                                                                     
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
Selecting previously unselected package insomnia.
(Reading database ... 187706 files and directories currently installed.)
Preparing to unpack .../insomnia_7.1.0_amd64.deb ...
Unpacking insomnia (7.1.0) ...
Setting up insomnia (7.1.0) ...
Processing triggers for hicolor-icon-theme (0.17-2) ...
Processing triggers for mime-support (3.60ubuntu1) ...
Processing triggers for desktop-file-utils (0.23-1ubuntu3.18.04.2) ...
Processing triggers for gnome-menus (3.13.3-11ubuntu1.1) ...
N: Ignoring file 'intel-sgx.l-ist' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
```

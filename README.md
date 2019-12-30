# trojan-gfw-prebuilt-raspbian-binary
Prebuilt trojan-gfw binary for Raspbian

## How to install

```
trojan -> /usr/local/bin/trojan
trojan.service -> /usr/lib/systemd/system/trojan.service
trojan@.service -> /usr/lib/systemd/system/trojan@.service
```

## Build guide

Please refer to the official guide: https://trojan-gfw.github.io/trojan/build

## Build platform (Raspi 2)

```
$ lscpu
Architecture:        armv7l
Byte Order:          Little Endian
CPU(s):              4
On-line CPU(s) list: 0-3
Thread(s) per core:  1
Core(s) per socket:  4
Socket(s):           1
Vendor ID:           ARM
Model:               5
Model name:          Cortex-A7
Stepping:            r0p5
CPU max MHz:         900.0000
CPU min MHz:         600.0000
BogoMIPS:            38.40
Flags:               half thumb fastmult vfp edsp neon vfpv3 tls vfpv4 idiva idivt vfpd32 lpae evtstrm

$ lsb_release -a
No LSB modules are available.
Distributor ID: Raspbian
Description:    Raspbian GNU/Linux 10 (buster)
Release:        10
Codename:       buster
```

## Full build log

```
$ sudo apt -y install build-essential cmake libboost-system-dev libboost-program-options-dev libssl-dev default-libmysqlclient-dev
Reading package lists... Done
Building dependency tree
Reading state information... Done
build-essential is already the newest version (12.6).
libssl-dev is already the newest version (1.1.1d-0+deb10u2).
The following additional packages will be installed:
  cmake-data libboost-program-options1.67-dev libboost-program-options1.67.0 libboost-system1.67-dev
  libboost1.67-dev libgmp-dev libgmpxx4ldbl libgnutls-dane0 libgnutls-openssl27 libgnutls28-dev libgnutlsxx28
  libidn2-dev libjsoncpp1 libmariadb-dev libmariadb-dev-compat libmariadb3 libp11-kit-dev librhash0
  libtasn1-6-dev libtasn1-doc libunbound8 mariadb-common mysql-common nettle-dev
Suggested packages:
  cmake-doc ninja-build libboost1.67-doc libboost-atomic1.67-dev libboost-chrono1.67-dev
  libboost-container1.67-dev libboost-context1.67-dev libboost-coroutine1.67-dev libboost-date-time1.67-dev
  libboost-exception1.67-dev libboost-fiber1.67-dev libboost-filesystem1.67-dev libboost-graph1.67-dev
  libboost-graph-parallel1.67-dev libboost-iostreams1.67-dev libboost-locale1.67-dev libboost-log1.67-dev
  libboost-math1.67-dev libboost-mpi1.67-dev libboost-mpi-python1.67-dev libboost-numpy1.67-dev
  libboost-python1.67-dev libboost-random1.67-dev libboost-regex1.67-dev libboost-serialization1.67-dev
  libboost-signals1.67-dev libboost-stacktrace1.67-dev libboost-test1.67-dev libboost-thread1.67-dev
  libboost-timer1.67-dev libboost-type-erasure1.67-dev libboost-wave1.67-dev libboost1.67-tools-dev
  libmpfrc++-dev libntl-dev gmp-doc libgmp10-doc libmpfr-dev gnutls-bin gnutls-doc
The following NEW packages will be installed:
  cmake cmake-data default-libmysqlclient-dev libboost-program-options-dev libboost-program-options1.67-dev
  libboost-program-options1.67.0 libboost-system-dev libboost-system1.67-dev libboost1.67-dev libgmp-dev
  libgmpxx4ldbl libgnutls-dane0 libgnutls-openssl27 libgnutls28-dev libgnutlsxx28 libidn2-dev libjsoncpp1
  libmariadb-dev libmariadb-dev-compat libmariadb3 libp11-kit-dev librhash0 libtasn1-6-dev libtasn1-doc
  libunbound8 mariadb-common mysql-common nettle-dev
0 upgraded, 28 newly installed, 0 to remove and 0 not upgraded.
Need to get 19.2 MB of archives.
After this operation, 177 MB of additional disk space will be used.
Get:1 http://muug.ca/mirror/raspbian/raspbian buster/main armhf cmake-data all 3.13.4-1 [1,476 kB]
Get:2 http://raspbian.mirror.colo-serv.net/raspbian buster/main armhf libjsoncpp1 armhf 1.7.4-3 [66.2 kB]
Get:3 http://muug.ca/mirror/raspbian/raspbian buster/main armhf librhash0 armhf 1.3.8-1 [132 kB]
Get:4 http://muug.ca/mirror/raspbian/raspbian buster/main armhf cmake armhf 3.13.4-1 [2,559 kB]
Get:9 http://mirrors.switch.ca/raspbian/raspbian buster/main armhf libgnutls-dane0 armhf 3.6.7-4 [314 kB]
Get:5 http://muug.ca/mirror/raspbian/raspbian buster/main armhf mysql-common all 5.8+1.0.5 [7,324 B]
Get:6 http://muug.ca/mirror/raspbian/raspbian buster/main armhf mariadb-common all 1:10.3.17-0+deb10u1 [31.6 kB]
Get:7 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libmariadb3 armhf 1:10.3.17-0+deb10u1 [157 kB]
Get:10 http://mirrors.switch.ca/raspbian/raspbian buster/main armhf libgnutls-openssl27 armhf 3.6.7-4 [314 kB]
Get:8 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libunbound8 armhf 1.9.0-2+deb10u1 [402 kB]
Get:22 http://mirrors.switch.ca/raspbian/raspbian buster/main armhf libboost1.67-dev armhf 1.67.0-13 [8,386 kB]
Get:23 http://mirrors.switch.ca/raspbian/raspbian buster/main armhf libboost-program-options1.67.0 armhf 1.67.0-13 [330 kB]
Get:24 http://mirrors.switch.ca/raspbian/raspbian buster/main armhf libboost-program-options1.67-dev armhf 1.67.0-13 [374 kB]
Get:11 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libgnutlsxx28 armhf 3.6.7-4 [11.8 kB]
Get:12 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libidn2-dev armhf 2.0.5-1 [76.1 kB]
Get:13 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libp11-kit-dev armhf 0.23.15-2 [195 kB]
Get:14 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libtasn1-6-dev armhf 4.13-3 [96.8 kB]
Get:15 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libgmpxx4ldbl armhf 2:6.1.2+dfsg-4 [21.8 kB]
Get:16 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libgmp-dev armhf 2:6.1.2+dfsg-4 [570 kB]
Get:17 http://muug.ca/mirror/raspbian/raspbian buster/main armhf nettle-dev armhf 3.4.1-1 [1,079 kB]
Get:18 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libgnutls28-dev armhf 3.6.7-4 [998 kB]
Get:19 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libmariadb-dev armhf 1:10.3.17-0+deb10u1 [992 kB]
Get:20 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libmariadb-dev-compat armhf 1:10.3.17-0+deb10u1 [30.8 kB]
Get:21 http://muug.ca/mirror/raspbian/raspbian buster/main armhf default-libmysqlclient-dev armhf 1.0.5 [3,764 B]
Get:25 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libboost-program-options-dev armhf 1.67.0.1+b1 [3,940 B]
Get:26 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libboost-system1.67-dev armhf 1.67.0-13 [230 kB]
Get:27 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libboost-system-dev armhf 1.67.0.1+b1 [4,060 B]
Get:28 http://muug.ca/mirror/raspbian/raspbian buster/main armhf libtasn1-doc all 4.13-3 [317 kB]
Fetched 19.2 MB in 2min 20s (137 kB/s)
Selecting previously unselected package cmake-data.
(Reading database ... 174878 files and directories currently installed.)
Preparing to unpack .../00-cmake-data_3.13.4-1_all.deb ...
Unpacking cmake-data (3.13.4-1) ...
Selecting previously unselected package libjsoncpp1:armhf.
Preparing to unpack .../01-libjsoncpp1_1.7.4-3_armhf.deb ...
Unpacking libjsoncpp1:armhf (1.7.4-3) ...
Selecting previously unselected package librhash0:armhf.
Preparing to unpack .../02-librhash0_1.3.8-1_armhf.deb ...
Unpacking librhash0:armhf (1.3.8-1) ...
Selecting previously unselected package cmake.
Preparing to unpack .../03-cmake_3.13.4-1_armhf.deb ...
Unpacking cmake (3.13.4-1) ...
Selecting previously unselected package mysql-common.
Preparing to unpack .../04-mysql-common_5.8+1.0.5_all.deb ...
Unpacking mysql-common (5.8+1.0.5) ...
Selecting previously unselected package mariadb-common.
Preparing to unpack .../05-mariadb-common_1%3a10.3.17-0+deb10u1_all.deb ...
Unpacking mariadb-common (1:10.3.17-0+deb10u1) ...
Selecting previously unselected package libmariadb3:armhf.
Preparing to unpack .../06-libmariadb3_1%3a10.3.17-0+deb10u1_armhf.deb ...
Unpacking libmariadb3:armhf (1:10.3.17-0+deb10u1) ...
Selecting previously unselected package libunbound8:armhf.
Preparing to unpack .../07-libunbound8_1.9.0-2+deb10u1_armhf.deb ...
Unpacking libunbound8:armhf (1.9.0-2+deb10u1) ...
Selecting previously unselected package libgnutls-dane0:armhf.
Preparing to unpack .../08-libgnutls-dane0_3.6.7-4_armhf.deb ...
Unpacking libgnutls-dane0:armhf (3.6.7-4) ...
Selecting previously unselected package libgnutls-openssl27:armhf.
Preparing to unpack .../09-libgnutls-openssl27_3.6.7-4_armhf.deb ...
Unpacking libgnutls-openssl27:armhf (3.6.7-4) ...
Selecting previously unselected package libgnutlsxx28:armhf.
Preparing to unpack .../10-libgnutlsxx28_3.6.7-4_armhf.deb ...
Unpacking libgnutlsxx28:armhf (3.6.7-4) ...
Selecting previously unselected package libidn2-dev:armhf.
Preparing to unpack .../11-libidn2-dev_2.0.5-1_armhf.deb ...
Unpacking libidn2-dev:armhf (2.0.5-1) ...
Selecting previously unselected package libp11-kit-dev:armhf.
Preparing to unpack .../12-libp11-kit-dev_0.23.15-2_armhf.deb ...
Unpacking libp11-kit-dev:armhf (0.23.15-2) ...
Selecting previously unselected package libtasn1-6-dev:armhf.
Preparing to unpack .../13-libtasn1-6-dev_4.13-3_armhf.deb ...
Unpacking libtasn1-6-dev:armhf (4.13-3) ...
Selecting previously unselected package libgmpxx4ldbl:armhf.
Preparing to unpack .../14-libgmpxx4ldbl_2%3a6.1.2+dfsg-4_armhf.deb ...
Unpacking libgmpxx4ldbl:armhf (2:6.1.2+dfsg-4) ...
Selecting previously unselected package libgmp-dev:armhf.
Preparing to unpack .../15-libgmp-dev_2%3a6.1.2+dfsg-4_armhf.deb ...
Unpacking libgmp-dev:armhf (2:6.1.2+dfsg-4) ...
Selecting previously unselected package nettle-dev:armhf.
Preparing to unpack .../16-nettle-dev_3.4.1-1_armhf.deb ...
Unpacking nettle-dev:armhf (3.4.1-1) ...
Selecting previously unselected package libgnutls28-dev:armhf.
Preparing to unpack .../17-libgnutls28-dev_3.6.7-4_armhf.deb ...
Unpacking libgnutls28-dev:armhf (3.6.7-4) ...
Selecting previously unselected package libmariadb-dev.
Preparing to unpack .../18-libmariadb-dev_1%3a10.3.17-0+deb10u1_armhf.deb ...
Unpacking libmariadb-dev (1:10.3.17-0+deb10u1) ...
Selecting previously unselected package libmariadb-dev-compat:armhf.
Preparing to unpack .../19-libmariadb-dev-compat_1%3a10.3.17-0+deb10u1_armhf.deb ...
Unpacking libmariadb-dev-compat:armhf (1:10.3.17-0+deb10u1) ...
Selecting previously unselected package default-libmysqlclient-dev:armhf.
Preparing to unpack .../20-default-libmysqlclient-dev_1.0.5_armhf.deb ...
Unpacking default-libmysqlclient-dev:armhf (1.0.5) ...
Selecting previously unselected package libboost1.67-dev:armhf.
Preparing to unpack .../21-libboost1.67-dev_1.67.0-13_armhf.deb ...
Unpacking libboost1.67-dev:armhf (1.67.0-13) ...
Selecting previously unselected package libboost-program-options1.67.0:armhf.
Preparing to unpack .../22-libboost-program-options1.67.0_1.67.0-13_armhf.deb ...
Unpacking libboost-program-options1.67.0:armhf (1.67.0-13) ...
Selecting previously unselected package libboost-program-options1.67-dev:armhf.
Preparing to unpack .../23-libboost-program-options1.67-dev_1.67.0-13_armhf.deb ...
Unpacking libboost-program-options1.67-dev:armhf (1.67.0-13) ...
Selecting previously unselected package libboost-program-options-dev:armhf.
Preparing to unpack .../24-libboost-program-options-dev_1.67.0.1+b1_armhf.deb ...
Unpacking libboost-program-options-dev:armhf (1.67.0.1+b1) ...
Selecting previously unselected package libboost-system1.67-dev:armhf.
Preparing to unpack .../25-libboost-system1.67-dev_1.67.0-13_armhf.deb ...
Unpacking libboost-system1.67-dev:armhf (1.67.0-13) ...
Selecting previously unselected package libboost-system-dev:armhf.
Preparing to unpack .../26-libboost-system-dev_1.67.0.1+b1_armhf.deb ...
Unpacking libboost-system-dev:armhf (1.67.0.1+b1) ...
Selecting previously unselected package libtasn1-doc.
Preparing to unpack .../27-libtasn1-doc_4.13-3_all.deb ...
Unpacking libtasn1-doc (4.13-3) ...
Setting up libboost1.67-dev:armhf (1.67.0-13) ...
Setting up libboost-program-options1.67.0:armhf (1.67.0-13) ...
Setting up mysql-common (5.8+1.0.5) ...
update-alternatives: using /etc/mysql/my.cnf.fallback to provide /etc/mysql/my.cnf (my.cnf) in auto mode
Setting up libgnutls-openssl27:armhf (3.6.7-4) ...
Setting up libboost-program-options1.67-dev:armhf (1.67.0-13) ...
Setting up libtasn1-doc (4.13-3) ...
Setting up mariadb-common (1:10.3.17-0+deb10u1) ...
update-alternatives: using /etc/mysql/mariadb.cnf to provide /etc/mysql/my.cnf (my.cnf) in auto mode
Setting up libunbound8:armhf (1.9.0-2+deb10u1) ...
Setting up libgmpxx4ldbl:armhf (2:6.1.2+dfsg-4) ...
Setting up libboost-program-options-dev:armhf (1.67.0.1+b1) ...
Setting up libmariadb3:armhf (1:10.3.17-0+deb10u1) ...
Setting up libgnutlsxx28:armhf (3.6.7-4) ...
Setting up libidn2-dev:armhf (2.0.5-1) ...
Setting up librhash0:armhf (1.3.8-1) ...
Setting up cmake-data (3.13.4-1) ...
Setting up libboost-system1.67-dev:armhf (1.67.0-13) ...
Setting up libtasn1-6-dev:armhf (4.13-3) ...
Setting up libp11-kit-dev:armhf (0.23.15-2) ...
Setting up libjsoncpp1:armhf (1.7.4-3) ...
Setting up libgnutls-dane0:armhf (3.6.7-4) ...
Setting up libgmp-dev:armhf (2:6.1.2+dfsg-4) ...
Setting up nettle-dev:armhf (3.4.1-1) ...
Setting up libboost-system-dev:armhf (1.67.0.1+b1) ...
Setting up cmake (3.13.4-1) ...
Setting up libgnutls28-dev:armhf (3.6.7-4) ...
Setting up libmariadb-dev (1:10.3.17-0+deb10u1) ...
Setting up libmariadb-dev-compat:armhf (1:10.3.17-0+deb10u1) ...
Setting up default-libmysqlclient-dev:armhf (1.0.5) ...
Processing triggers for man-db (2.8.5-2) ...
Processing triggers for install-info (6.5.0.dfsg.1-4+b1) ...
Processing triggers for libc-bin (2.28-10+rpi1) ...
$ cd /tmp
$ git clone https://github.com/trojan-gfw/trojan.git
Cloning into 'trojan'...
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 2434 (delta 0), reused 1 (delta 0), pack-reused 2429
Receiving objects: 100% (2434/2434), 853.27 KiB | 2.44 MiB/s, done.
Resolving deltas: 100% (1821/1821), done.
$ cd trojan/
$ mkdir build
$ cd build/
$ cmake ..
-- The C compiler identification is GNU 8.3.0
-- The CXX compiler identification is GNU 8.3.0
-- Check for working C compiler: /usr/bin/cc
-- Check for working C compiler: /usr/bin/cc -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /usr/bin/c++
-- Check for working CXX compiler: /usr/bin/c++ -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Looking for pthread.h
-- Looking for pthread.h - found
-- Looking for pthread_create
-- Looking for pthread_create - not found
-- Check if compiler accepts -pthread
-- Check if compiler accepts -pthread - yes
-- Found Threads: TRUE
-- Boost version: 1.67.0
-- Found the following Boost libraries:
--   system
--   program_options
-- Found OpenSSL: /usr/lib/arm-linux-gnueabihf/libcrypto.so (found suitable version "1.1.1d", minimum required is "1.1.0")
-- Found MySQL: /usr/lib/arm-linux-gnueabihf/libmysqlclient.so
-- Configuring done
-- Generating done
-- Build files have been written to: /tmp/trojan/build
$ make
Scanning dependencies of target trojan
[  5%] Building CXX object CMakeFiles/trojan.dir/src/core/authenticator.cpp.o
[ 11%] Building CXX object CMakeFiles/trojan.dir/src/core/config.cpp.o
[ 16%] Building CXX object CMakeFiles/trojan.dir/src/core/log.cpp.o
[ 22%] Building CXX object CMakeFiles/trojan.dir/src/core/service.cpp.o
[ 27%] Building CXX object CMakeFiles/trojan.dir/src/core/version.cpp.o
[ 33%] Building CXX object CMakeFiles/trojan.dir/src/main.cpp.o
[ 38%] Building CXX object CMakeFiles/trojan.dir/src/proto/socks5address.cpp.o
[ 44%] Building CXX object CMakeFiles/trojan.dir/src/proto/trojanrequest.cpp.o
[ 50%] Building CXX object CMakeFiles/trojan.dir/src/proto/udppacket.cpp.o
[ 55%] Building CXX object CMakeFiles/trojan.dir/src/session/clientsession.cpp.o
In file included from /usr/include/c++/8/vector:69,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/clientsession.h:23,
                 from /tmp/trojan/src/session/clientsession.cpp:20:
/usr/include/c++/8/bits/vector.tcc: In member function ‘void std::vector<_Tp, _Alloc>::_M_realloc_insert(std::vector<_Tp, _Alloc>::iterator, _Args&& ...) [with _Args = {const boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry&}; _Tp = boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry; _Alloc = std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry>]’:
/usr/include/c++/8/bits/vector.tcc:413:7: note: parameter passing for argument of type ‘std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> >::iterator’ {aka ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> > >’} changed in GCC 7.1
       vector<_Tp, _Alloc>::
       ^~~~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:64,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/clientsession.h:23,
                 from /tmp/trojan/src/session/clientsession.cpp:20:
/usr/include/c++/8/bits/stl_vector.h: In member function ‘void boost::asio::detail::epoll_reactor::schedule_timer(boost::asio::detail::timer_queue<Time_Traits>&, const typename Time_Traits::time_type&, typename boost::asio::detail::timer_queue<Time_Traits>::per_timer_data&, boost::asio::detail::wait_op*) [with Time_Traits = boost::asio::time_traits<boost::posix_time::ptime>]’:
/usr/include/c++/8/bits/stl_vector.h:1085:4: note: parameter passing for argument of type ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> > >’ changed in GCC 7.1
    _M_realloc_insert(end(), __x);
    ^~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:69,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/clientsession.h:23,
                 from /tmp/trojan/src/session/clientsession.cpp:20:
/usr/include/c++/8/bits/vector.tcc: In member function ‘void std::vector<_Tp, _Alloc>::_M_realloc_insert(std::vector<_Tp, _Alloc>::iterator, _Args&& ...) [with _Args = {const boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry&}; _Tp = boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry; _Alloc = std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry>]’:
/usr/include/c++/8/bits/vector.tcc:413:7: note: parameter passing for argument of type ‘std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> >::iterator’ {aka ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> > >’} changed in GCC 7.1
       vector<_Tp, _Alloc>::
       ^~~~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:64,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/clientsession.h:23,
                 from /tmp/trojan/src/session/clientsession.cpp:20:
/usr/include/c++/8/bits/stl_vector.h: In member function ‘void boost::asio::detail::epoll_reactor::schedule_timer(boost::asio::detail::timer_queue<Time_Traits>&, const typename Time_Traits::time_type&, typename boost::asio::detail::timer_queue<Time_Traits>::per_timer_data&, boost::asio::detail::wait_op*) [with Time_Traits = boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> >]’:
/usr/include/c++/8/bits/stl_vector.h:1085:4: note: parameter passing for argument of type ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> > >’ changed in GCC 7.1
    _M_realloc_insert(end(), __x);
    ^~~~~~~~~~~~~~~~~
[ 61%] Building CXX object CMakeFiles/trojan.dir/src/session/forwardsession.cpp.o
In file included from /usr/include/c++/8/vector:69,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/forwardsession.h:23,
                 from /tmp/trojan/src/session/forwardsession.cpp:20:
/usr/include/c++/8/bits/vector.tcc: In member function ‘void std::vector<_Tp, _Alloc>::_M_realloc_insert(std::vector<_Tp, _Alloc>::iterator, _Args&& ...) [with _Args = {const boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry&}; _Tp = boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry; _Alloc = std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry>]’:
/usr/include/c++/8/bits/vector.tcc:413:7: note: parameter passing for argument of type ‘std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> >::iterator’ {aka ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> > >’} changed in GCC 7.1
       vector<_Tp, _Alloc>::
       ^~~~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:64,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/forwardsession.h:23,
                 from /tmp/trojan/src/session/forwardsession.cpp:20:
/usr/include/c++/8/bits/stl_vector.h: In member function ‘void boost::asio::detail::epoll_reactor::schedule_timer(boost::asio::detail::timer_queue<Time_Traits>&, const typename Time_Traits::time_type&, typename boost::asio::detail::timer_queue<Time_Traits>::per_timer_data&, boost::asio::detail::wait_op*) [with Time_Traits = boost::asio::time_traits<boost::posix_time::ptime>]’:
/usr/include/c++/8/bits/stl_vector.h:1085:4: note: parameter passing for argument of type ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> > >’ changed in GCC 7.1
    _M_realloc_insert(end(), __x);
    ^~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:69,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/forwardsession.h:23,
                 from /tmp/trojan/src/session/forwardsession.cpp:20:
/usr/include/c++/8/bits/vector.tcc: In member function ‘void std::vector<_Tp, _Alloc>::_M_realloc_insert(std::vector<_Tp, _Alloc>::iterator, _Args&& ...) [with _Args = {const boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry&}; _Tp = boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry; _Alloc = std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry>]’:
/usr/include/c++/8/bits/vector.tcc:413:7: note: parameter passing for argument of type ‘std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> >::iterator’ {aka ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> > >’} changed in GCC 7.1
       vector<_Tp, _Alloc>::
       ^~~~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:64,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/forwardsession.h:23,
                 from /tmp/trojan/src/session/forwardsession.cpp:20:
/usr/include/c++/8/bits/stl_vector.h: In member function ‘void boost::asio::detail::epoll_reactor::schedule_timer(boost::asio::detail::timer_queue<Time_Traits>&, const typename Time_Traits::time_type&, typename boost::asio::detail::timer_queue<Time_Traits>::per_timer_data&, boost::asio::detail::wait_op*) [with Time_Traits = boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> >]’:
/usr/include/c++/8/bits/stl_vector.h:1085:4: note: parameter passing for argument of type ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> > >’ changed in GCC 7.1
    _M_realloc_insert(end(), __x);
    ^~~~~~~~~~~~~~~~~
[ 66%] Building CXX object CMakeFiles/trojan.dir/src/session/natsession.cpp.o
In file included from /usr/include/c++/8/vector:69,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/natsession.h:23,
                 from /tmp/trojan/src/session/natsession.cpp:20:
/usr/include/c++/8/bits/vector.tcc: In member function ‘void std::vector<_Tp, _Alloc>::_M_realloc_insert(std::vector<_Tp, _Alloc>::iterator, _Args&& ...) [with _Args = {const boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry&}; _Tp = boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry; _Alloc = std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry>]’:
/usr/include/c++/8/bits/vector.tcc:413:7: note: parameter passing for argument of type ‘std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> >::iterator’ {aka ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> > >’} changed in GCC 7.1
       vector<_Tp, _Alloc>::
       ^~~~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:64,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/natsession.h:23,
                 from /tmp/trojan/src/session/natsession.cpp:20:
/usr/include/c++/8/bits/stl_vector.h: In member function ‘void boost::asio::detail::epoll_reactor::schedule_timer(boost::asio::detail::timer_queue<Time_Traits>&, const typename Time_Traits::time_type&, typename boost::asio::detail::timer_queue<Time_Traits>::per_timer_data&, boost::asio::detail::wait_op*) [with Time_Traits = boost::asio::time_traits<boost::posix_time::ptime>]’:
/usr/include/c++/8/bits/stl_vector.h:1085:4: note: parameter passing for argument of type ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> > >’ changed in GCC 7.1
    _M_realloc_insert(end(), __x);
    ^~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:69,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/natsession.h:23,
                 from /tmp/trojan/src/session/natsession.cpp:20:
/usr/include/c++/8/bits/vector.tcc: In member function ‘void std::vector<_Tp, _Alloc>::_M_realloc_insert(std::vector<_Tp, _Alloc>::iterator, _Args&& ...) [with _Args = {const boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry&}; _Tp = boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry; _Alloc = std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry>]’:
/usr/include/c++/8/bits/vector.tcc:413:7: note: parameter passing for argument of type ‘std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> >::iterator’ {aka ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> > >’} changed in GCC 7.1
       vector<_Tp, _Alloc>::
       ^~~~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:64,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/natsession.h:23,
                 from /tmp/trojan/src/session/natsession.cpp:20:
/usr/include/c++/8/bits/stl_vector.h: In member function ‘void boost::asio::detail::epoll_reactor::schedule_timer(boost::asio::detail::timer_queue<Time_Traits>&, const typename Time_Traits::time_type&, typename boost::asio::detail::timer_queue<Time_Traits>::per_timer_data&, boost::asio::detail::wait_op*) [with Time_Traits = boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> >]’:
/usr/include/c++/8/bits/stl_vector.h:1085:4: note: parameter passing for argument of type ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> > >’ changed in GCC 7.1
    _M_realloc_insert(end(), __x);
    ^~~~~~~~~~~~~~~~~
[ 72%] Building CXX object CMakeFiles/trojan.dir/src/session/serversession.cpp.o
In file included from /usr/include/c++/8/vector:69,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/serversession.h:23,
                 from /tmp/trojan/src/session/serversession.cpp:20:
/usr/include/c++/8/bits/vector.tcc: In member function ‘void std::vector<_Tp, _Alloc>::_M_realloc_insert(std::vector<_Tp, _Alloc>::iterator, _Args&& ...) [with _Args = {const boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry&}; _Tp = boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry; _Alloc = std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry>]’:
/usr/include/c++/8/bits/vector.tcc:413:7: note: parameter passing for argument of type ‘std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> >::iterator’ {aka ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> > >’} changed in GCC 7.1
       vector<_Tp, _Alloc>::
       ^~~~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:64,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/serversession.h:23,
                 from /tmp/trojan/src/session/serversession.cpp:20:
/usr/include/c++/8/bits/stl_vector.h: In member function ‘void boost::asio::detail::epoll_reactor::schedule_timer(boost::asio::detail::timer_queue<Time_Traits>&, const typename Time_Traits::time_type&, typename boost::asio::detail::timer_queue<Time_Traits>::per_timer_data&, boost::asio::detail::wait_op*) [with Time_Traits = boost::asio::time_traits<boost::posix_time::ptime>]’:
/usr/include/c++/8/bits/stl_vector.h:1085:4: note: parameter passing for argument of type ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> > >’ changed in GCC 7.1
    _M_realloc_insert(end(), __x);
    ^~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:69,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/serversession.h:23,
                 from /tmp/trojan/src/session/serversession.cpp:20:
/usr/include/c++/8/bits/vector.tcc: In member function ‘void std::vector<_Tp, _Alloc>::_M_realloc_insert(std::vector<_Tp, _Alloc>::iterator, _Args&& ...) [with _Args = {const boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry&}; _Tp = boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry; _Alloc = std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry>]’:
/usr/include/c++/8/bits/vector.tcc:413:7: note: parameter passing for argument of type ‘std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> >::iterator’ {aka ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> > >’} changed in GCC 7.1
       vector<_Tp, _Alloc>::
       ^~~~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:64,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/serversession.h:23,
                 from /tmp/trojan/src/session/serversession.cpp:20:
/usr/include/c++/8/bits/stl_vector.h: In member function ‘void boost::asio::detail::epoll_reactor::schedule_timer(boost::asio::detail::timer_queue<Time_Traits>&, const typename Time_Traits::time_type&, typename boost::asio::detail::timer_queue<Time_Traits>::per_timer_data&, boost::asio::detail::wait_op*) [with Time_Traits = boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> >]’:
/usr/include/c++/8/bits/stl_vector.h:1085:4: note: parameter passing for argument of type ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> > >’ changed in GCC 7.1
    _M_realloc_insert(end(), __x);
    ^~~~~~~~~~~~~~~~~
[ 77%] Building CXX object CMakeFiles/trojan.dir/src/session/session.cpp.o
[ 83%] Building CXX object CMakeFiles/trojan.dir/src/session/udpforwardsession.cpp.o
In file included from /usr/include/c++/8/vector:69,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/udpforwardsession.h:23,
                 from /tmp/trojan/src/session/udpforwardsession.cpp:20:
/usr/include/c++/8/bits/vector.tcc: In member function ‘void std::vector<_Tp, _Alloc>::_M_realloc_insert(std::vector<_Tp, _Alloc>::iterator, _Args&& ...) [with _Args = {const boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry&}; _Tp = boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry; _Alloc = std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry>]’:
/usr/include/c++/8/bits/vector.tcc:413:7: note: parameter passing for argument of type ‘std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> >::iterator’ {aka ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> > >’} changed in GCC 7.1
       vector<_Tp, _Alloc>::
       ^~~~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:64,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/udpforwardsession.h:23,
                 from /tmp/trojan/src/session/udpforwardsession.cpp:20:
/usr/include/c++/8/bits/stl_vector.h: In member function ‘void boost::asio::detail::epoll_reactor::schedule_timer(boost::asio::detail::timer_queue<Time_Traits>&, const typename Time_Traits::time_type&, typename boost::asio::detail::timer_queue<Time_Traits>::per_timer_data&, boost::asio::detail::wait_op*) [with Time_Traits = boost::asio::time_traits<boost::posix_time::ptime>]’:
/usr/include/c++/8/bits/stl_vector.h:1085:4: note: parameter passing for argument of type ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::forwarding_posix_time_traits>::heap_entry> > >’ changed in GCC 7.1
    _M_realloc_insert(end(), __x);
    ^~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:69,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/udpforwardsession.h:23,
                 from /tmp/trojan/src/session/udpforwardsession.cpp:20:
/usr/include/c++/8/bits/vector.tcc: In member function ‘void std::vector<_Tp, _Alloc>::_M_realloc_insert(std::vector<_Tp, _Alloc>::iterator, _Args&& ...) [with _Args = {const boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry&}; _Tp = boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry; _Alloc = std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry>]’:
/usr/include/c++/8/bits/vector.tcc:413:7: note: parameter passing for argument of type ‘std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> >::iterator’ {aka ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> > >’} changed in GCC 7.1
       vector<_Tp, _Alloc>::
       ^~~~~~~~~~~~~~~~~~~
In file included from /usr/include/c++/8/vector:64,
                 from /usr/include/boost/asio/detail/impl/service_registry.ipp:19,
                 from /usr/include/boost/asio/detail/service_registry.hpp:163,
                 from /usr/include/boost/asio/impl/execution_context.hpp:20,
                 from /usr/include/boost/asio/execution_context.hpp:408,
                 from /usr/include/boost/asio/detail/scheduler.hpp:21,
                 from /usr/include/boost/asio/system_context.hpp:19,
                 from /usr/include/boost/asio/impl/system_executor.hpp:22,
                 from /usr/include/boost/asio/system_executor.hpp:129,
                 from /usr/include/boost/asio/associated_executor.hpp:21,
                 from /usr/include/boost/asio/detail/bind_handler.hpp:20,
                 from /usr/include/boost/asio/detail/wrapped_handler.hpp:18,
                 from /usr/include/boost/asio/io_context.hpp:24,
                 from /tmp/trojan/src/session/session.h:25,
                 from /tmp/trojan/src/session/udpforwardsession.h:23,
                 from /tmp/trojan/src/session/udpforwardsession.cpp:20:
/usr/include/c++/8/bits/stl_vector.h: In member function ‘void boost::asio::detail::epoll_reactor::schedule_timer(boost::asio::detail::timer_queue<Time_Traits>&, const typename Time_Traits::time_type&, typename boost::asio::detail::timer_queue<Time_Traits>::per_timer_data&, boost::asio::detail::wait_op*) [with Time_Traits = boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> >]’:
/usr/include/c++/8/bits/stl_vector.h:1085:4: note: parameter passing for argument of type ‘__gnu_cxx::__normal_iterator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry*, std::vector<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry, std::allocator<boost::asio::detail::timer_queue<boost::asio::detail::chrono_time_traits<std::chrono::_V2::steady_clock, boost::asio::wait_traits<std::chrono::_V2::steady_clock> > >::heap_entry> > >’ changed in GCC 7.1
    _M_realloc_insert(end(), __x);
    ^~~~~~~~~~~~~~~~~
[ 88%] Building CXX object CMakeFiles/trojan.dir/src/ssl/ssldefaults.cpp.o
[ 94%] Building CXX object CMakeFiles/trojan.dir/src/ssl/sslsession.cpp.o
[100%] Linking CXX executable trojan
[100%] Built target trojan
$ ctest
Test project /tmp/trojan/build
    Start 1: LinuxSmokeTest-basic
1/2 Test #1: LinuxSmokeTest-basic .............   Passed    7.53 sec
    Start 2: LinuxSmokeTest-fake-client
2/2 Test #2: LinuxSmokeTest-fake-client .......   Passed    5.58 sec

100% tests passed, 0 tests failed out of 2

Total Test time (real) =  13.13 sec
$ sudo make install
[100%] Built target trojan
Install the project...
-- Install configuration: "Release"
-- Installing: /usr/local/bin/trojan
-- Installing: /usr/local/etc/trojan/config.json
-- Installing: /usr/local/share/man/man1/trojan.1
-- Installing: /usr/local/share/doc/trojan
-- Installing: /usr/local/share/doc/trojan/protocol.md
-- Installing: /usr/local/share/doc/trojan/README.md
-- Installing: /usr/local/share/doc/trojan/usage.md
-- Installing: /usr/local/share/doc/trojan/config.md
-- Installing: /usr/local/share/doc/trojan/build.md
-- Installing: /usr/local/share/doc/trojan/authenticator.md
-- Installing: /usr/local/share/doc/trojan/overview.md
-- Installing: /usr/local/share/doc/trojan/examples
-- Installing: /usr/local/share/doc/trojan/examples/client.json-example
-- Installing: /usr/local/share/doc/trojan/examples/forward.json-example
-- Installing: /usr/local/share/doc/trojan/examples/server.json-example
-- Installing: /usr/local/share/doc/trojan/examples/nat.json-example
-- Installing: /usr/lib/systemd/system/trojan.service
-- Installing: /usr/lib/systemd/system/trojan@.service
```

## License

Same as https://github.com/trojan-gfw/trojan

### Installing Library and Troubleshooting

cmake did not want to work with lcpprest. I had to change some options in the CMakeLists.txt

I use this reference to solve a big problem:
https://stackoverflow.com/questions/16710047/usr-bin-ld-cannot-find-lnameofthelibrary/42339395



```
➜  osc_la git:(master) ✗ rm -rf build 
➜  osc_la git:(master) ✗ mkdir build && cd build
➜  build git:(master) ✗ cmake ..
-- The C compiler identification is GNU 7.4.0
-- The CXX compiler identification is GNU 7.4.0
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
-- Looking for pthread_create in pthreads
-- Looking for pthread_create in pthreads - not found
-- Looking for pthread_create in pthread
-- Looking for pthread_create in pthread - found
-- Found Threads: TRUE  
-- Looking for crypto library - found
-- Looking for dl library - found
VERBOSE-- Looking for sgx_enclave_common library - found
CMake Warning at /opt/openenclave/lib/openenclave/cmake/openenclave-config.cmake:139 (message):
  -- Looking for sgx_dcap_ql library - not found.  Attestations based on
  quotes would not function without the quote provider.
Call Stack (most recent call first):
  CMakeLists.txt:8 (find_package)


-- Performing Test OE_SPECTRE_MITIGATION_C_FLAGS_SUPPORTED
-- Performing Test OE_SPECTRE_MITIGATION_C_FLAGS_SUPPORTED - Failed
-- Performing Test OE_SPECTRE_MITIGATION_CXX_FLAGS_SUPPORTED
-- Performing Test OE_SPECTRE_MITIGATION_CXX_FLAGS_SUPPORTED - Failed
CMake Error at host/CMakeLists.txt:10 (find_package):
  By not providing "Findcpprestsdk.cmake" in CMAKE_MODULE_PATH this project
  has asked CMake to find a package configuration file provided by
  "cpprestsdk", but CMake did not find one.

  Could not find a package configuration file provided by "cpprestsdk" with
  any of the following names:

    cpprestsdkConfig.cmake
    cpprestsdk-config.cmake

  Add the installation prefix of "cpprestsdk" to CMAKE_PREFIX_PATH or set
  "cpprestsdk_DIR" to a directory containing one of the above files.  If
  "cpprestsdk" provides a separate development package or SDK, be sure it has
  been installed.


-- Configuring incomplete, errors occurred!
See also "/home/spalacio/repos/openenclave/samples/osc_la/build/CMakeFiles/CMakeOutput.log".
See also "/home/spalacio/repos/openenclave/samples/osc_la/build/CMakeFiles/CMakeError.log".
➜  build git:(master) ✗ vim /usr/lib/x86_64-linux-gnu/cmake/cpprestsdk-config.cmake
➜  build git:(master) ✗ echo $cpprestsdk

➜  build git:(master) ✗ set cpprestsdk=/usr/lib/x86_64-linux-gnu/cmake/
➜  build git:(master) ✗ echo $cpprestsdk                               

➜  build git:(master) ✗ export cpprestsdk=/usr/lib/x86_64-linux-gnu/cmake/ 
➜  build git:(master) ✗ echo $cpprestsdk
/usr/lib/x86_64-linux-gnu/cmake/
➜  build git:(master) ✗ echo $CMAKE_PREFIX_PATH

➜  build git:(master) ✗ export CMAKE_PREFIX_PATH=/usr/lib/x86_64-linux-gnu/cmake/
➜  build git:(master) ✗ echo $CMAKE_PREFIX_PATH                                  
/usr/lib/x86_64-linux-gnu/cmake/
➜  build git:(master) ✗ pwd
/home/spalacio/repos/openenclave/samples/osc_la/build
➜  build git:(master) ✗ cd ..
➜  osc_la git:(master) ✗ rm -rf build
➜  osc_la git:(master) ✗ mkdir build && cd build
➜  build git:(master) ✗ cmake ..
-- The C compiler identification is GNU 7.4.0
-- The CXX compiler identification is GNU 7.4.0
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
-- Looking for pthread_create in pthreads
-- Looking for pthread_create in pthreads - not found
-- Looking for pthread_create in pthread
-- Looking for pthread_create in pthread - found
-- Found Threads: TRUE  
-- Looking for crypto library - found
-- Looking for dl library - found
VERBOSE-- Looking for sgx_enclave_common library - found
CMake Warning at /opt/openenclave/lib/openenclave/cmake/openenclave-config.cmake:139 (message):
  -- Looking for sgx_dcap_ql library - not found.  Attestations based on
  quotes would not function without the quote provider.
Call Stack (most recent call first):
  CMakeLists.txt:8 (find_package)


-- Performing Test OE_SPECTRE_MITIGATION_C_FLAGS_SUPPORTED
-- Performing Test OE_SPECTRE_MITIGATION_C_FLAGS_SUPPORTED - Failed
-- Performing Test OE_SPECTRE_MITIGATION_CXX_FLAGS_SUPPORTED
-- Performing Test OE_SPECTRE_MITIGATION_CXX_FLAGS_SUPPORTED - Failed
-- Found ZLIB: /usr/lib/x86_64-linux-gnu/libz.so (found version "1.2.11") 
-- Found OpenSSL: /usr/lib/x86_64-linux-gnu/libcrypto.so (found version "1.1.1")  
-- Configuring done
-- Generating done
-- Build files have been written to: /home/spalacio/repos/openenclave/samples/osc_la/build
➜  build git:(master) ✗ make run
[  4%] Generating localattestation_u.h, localattestation_u.c, localattestation_args.h
Generating edge routines for the Open Enclave SDK.
Success.
Scanning dependencies of target local_attestation_host
[  9%] Building CXX object host/CMakeFiles/local_attestation_host.dir/host.cpp.o
[ 13%] Building C object host/CMakeFiles/local_attestation_host.dir/localattestation_u.c.o
[ 18%] Linking CXX executable local_attestation_host
/usr/bin/ld: CMakeFiles/local_attestation_host.dir/host.cpp.o: undefined reference to symbol '_ZN5boost6system15system_categoryEv'
//usr/lib/x86_64-linux-gnu/libboost_system.so.1.65.1: error adding symbols: DSO missing from command line
collect2: error: ld returned 1 exit status
host/CMakeFiles/local_attestation_host.dir/build.make:115: recipe for target 'host/local_attestation_host' failed
make[3]: *** [host/local_attestation_host] Error 1
CMakeFiles/Makefile2:472: recipe for target 'host/CMakeFiles/local_attestation_host.dir/all' failed
make[2]: *** [host/CMakeFiles/local_attestation_host.dir/all] Error 2
CMakeFiles/Makefile2:118: recipe for target 'CMakeFiles/run.dir/rule' failed
make[1]: *** [CMakeFiles/run.dir/rule] Error 2
Makefile:131: recipe for target 'run' failed
make: *** [run] Error 2
➜  build git:(master) ✗ cd ..
➜  osc_la git:(master) ✗ rm -rf build 
➜  osc_la git:(master) ✗ mkdir build && cd build
➜  build git:(master) ✗ cmake ..
-- The C compiler identification is GNU 7.4.0
-- The CXX compiler identification is GNU 7.4.0
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
-- Looking for pthread_create in pthreads
-- Looking for pthread_create in pthreads - not found
-- Looking for pthread_create in pthread
-- Looking for pthread_create in pthread - found
-- Found Threads: TRUE  
-- Looking for crypto library - found
-- Looking for dl library - found
VERBOSE-- Looking for sgx_enclave_common library - found
CMake Warning at /opt/openenclave/lib/openenclave/cmake/openenclave-config.cmake:139 (message):
  -- Looking for sgx_dcap_ql library - not found.  Attestations based on
  quotes would not function without the quote provider.
Call Stack (most recent call first):
  CMakeLists.txt:8 (find_package)


-- Performing Test OE_SPECTRE_MITIGATION_C_FLAGS_SUPPORTED
-- Performing Test OE_SPECTRE_MITIGATION_C_FLAGS_SUPPORTED - Failed
-- Performing Test OE_SPECTRE_MITIGATION_CXX_FLAGS_SUPPORTED
-- Performing Test OE_SPECTRE_MITIGATION_CXX_FLAGS_SUPPORTED - Failed
-- Found ZLIB: /usr/lib/x86_64-linux-gnu/libz.so (found version "1.2.11") 
-- Found OpenSSL: /usr/lib/x86_64-linux-gnu/libcrypto.so (found version "1.1.1")  
-- Boost version: 1.65.1
-- Found the following Boost libraries:
--   system
-- Configuring done
-- Generating done
-- Build files have been written to: /home/spalacio/repos/openenclave/samples/osc_la/build
➜  build git:(master) ✗ make run
[  4%] Generating localattestation_t.h, localattestation_t.c, localattestation_args.h
Generating edge routines for the Open Enclave SDK.
Success.
Scanning dependencies of target common
[  9%] Building CXX object common/CMakeFiles/common.dir/attestation.cpp.o
[ 13%] Building CXX object common/CMakeFiles/common.dir/crypto.cpp.o
[ 18%] Building CXX object common/CMakeFiles/common.dir/dispatcher.cpp.o
[ 22%] Building C object common/CMakeFiles/common.dir/localattestation_t.c.o
[ 27%] Linking CXX static library libcommon.a
[ 27%] Built target common
Scanning dependencies of target public_key_a
[ 31%] Generating private_a.pem, public_a.pem
Generating RSA private key, 3072 bit long modulus (2 primes)
...........................................++++
.........++++
e is 3 (0x03)
writing RSA key
[ 31%] Built target public_key_a
[ 36%] Generating enclave_a_pubkey.h
Scanning dependencies of target enclave_b
[ 40%] Building CXX object enclave_b/CMakeFiles/enclave_b.dir/ecalls.cpp.o
[ 45%] Linking CXX executable enclave_b
[ 45%] Built target enclave_b
Scanning dependencies of target enclave_b_signed
[ 50%] Generating private_b.pem, public_b.pem
Generating RSA private key, 3072 bit long modulus (2 primes)
............................................++++
.++++
e is 3 (0x03)
writing RSA key
[ 54%] Generating enclave_b.signed
Created /home/spalacio/repos/openenclave/samples/osc_la/build/enclave_b/enclave_b.signed
[ 54%] Built target enclave_b_signed
Scanning dependencies of target public_key_b
[ 59%] Built target public_key_b
[ 63%] Generating enclave_b_pubkey.h
Scanning dependencies of target enclave_a
[ 68%] Building CXX object enclave_a/CMakeFiles/enclave_a.dir/ecalls.cpp.o
[ 72%] Linking CXX executable enclave_a
[ 72%] Built target enclave_a
Scanning dependencies of target enclave_a_signed
[ 77%] Generating enclave_a.signed
Created /home/spalacio/repos/openenclave/samples/osc_la/build/enclave_a/enclave_a.signed
[ 81%] Built target enclave_a_signed
Scanning dependencies of target sign
[ 81%] Built target sign
[ 86%] Generating localattestation_u.h, localattestation_u.c, localattestation_args.h
Generating edge routines for the Open Enclave SDK.
Success.
Scanning dependencies of target local_attestation_host
[ 90%] Building CXX object host/CMakeFiles/local_attestation_host.dir/host.cpp.o
[ 95%] Building C object host/CMakeFiles/local_attestation_host.dir/localattestation_u.c.o
[100%] Linking CXX executable local_attestation_host
[100%] Built target local_attestation_host
Scanning dependencies of target run
====== using cpp libraries ======
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/crypto.cpp(76): mbedtls initialized.
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/crypto.cpp(76): mbedtls initialized.
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(89): get_target_info
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/attestation.cpp(55): generate_local_report succeeded.
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(103): report_size = 448
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(114): info_size = 512
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(162): get_targeted_report_with_pubkey
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/attestation.cpp(55): generate_local_report succeeded.
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(204): get_targeted_report_with_pubkey succeeded
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/attestation.cpp(92): report_size = 448
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/attestation.cpp(103): oe_verify_report succeeded

Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/attestation.cpp(162): attestation succeeded.
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(256): verify_report_and_set_pubkey succeeded.
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(89): get_target_info
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/attestation.cpp(55): generate_local_report succeeded.
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(103): report_size = 448
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(114): info_size = 512
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/enclave_a/ecalls.cpp(51): enter get_targeted_report_with_pubkey
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(162): get_targeted_report_with_pubkey
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/attestation.cpp(55): generate_local_report succeeded.
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(204): get_targeted_report_with_pubkey succeeded
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/attestation.cpp(92): report_size = 448
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/attestation.cpp(103): oe_verify_report succeeded

Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/attestation.cpp(162): attestation succeeded.
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(256): verify_report_and_set_pubkey succeeded.
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/crypto.cpp(162): Padding used: MBEDTLS_RSA_PKCS_V21 for OAEP or PSS
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(286): enclave: generate_encrypted_message: encrypted_data_size = 256
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(322): Decrypted data: 
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(345): Decrypted data matches with the enclave internal secret data: descryption validation succeeded
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/crypto.cpp(162): Padding used: MBEDTLS_RSA_PKCS_V21 for OAEP or PSS
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(286): enclave: generate_encrypted_message: encrypted_data_size = 256
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(322): Decrypted data: 
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/dispatcher.cpp(345): Decrypted data matches with the enclave internal secret data: descryption validation succeeded
Enclave1: ***/home/spalacio/repos/openenclave/samples/osc_la/common/crypto.cpp(90): mbedtls cleaned up.
Enclave2: ***/home/spalacio/repos/openenclave/samples/osc_la/common/crypto.cpp(90): mbedtls cleaned up.
[100%] Built target run
```

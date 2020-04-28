# Homomorphic encryption

## Microsoft SEAL

```
cmake .                                                                                                28.04.20    19:37:34 
-- The CXX compiler identification is AppleClang 11.0.3.11030032
-- The C compiler identification is AppleClang 11.0.3.11030032
-- Check for working CXX compiler: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/c++
-- Check for working CXX compiler: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/c++ - works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Check for working C compiler: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/cc
-- Check for working C compiler: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/cc - works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Build type (CMAKE_BUILD_TYPE): Release
-- Microsoft SEAL debug mode: OFF
-- Setting up MSGSL ...
Cloning into 'src'...
HEAD is now at 7e99e76 Merge pull request #826 from JordanMaples/dev/jomaples/ctad_fix_v2
-- Found Git: /usr/bin/git (found version "2.24.1 (Apple Git-126)")
-- Setting up ZLIB ...
Cloning into 'src'...
HEAD is now at cacf7f1 zlib 1.2.11
-- Looking for sys/types.h
-- Looking for sys/types.h - found
-- Looking for stdint.h
-- Looking for stdint.h - found
-- Looking for stddef.h
-- Looking for stddef.h - found
-- Check size of off64_t
-- Check size of off64_t - failed
-- Looking for fseeko
-- Looking for fseeko - found
-- Looking for unistd.h
-- Looking for unistd.h - found
-- Looking for C++ include x86intrin.h
-- Looking for C++ include x86intrin.h - found
-- Looking for pthread.h
-- Looking for pthread.h - found
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD - Success
-- Found Threads: TRUE
-- Check size of size_t
-- Check size of size_t - done
-- Configuring done
-- Generating done
-- Build files have been written to: /Users/maverickzhn/repos/trellisfw/agapecert-osc/he/SEAL
```

```
  make                                                                                                   28.04.20    19:39:00 
Scanning dependencies of target zlibstatic
[  1%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/adler32.o
[  3%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/compress.o
[  5%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/crc32.o
[  7%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/deflate.o
[  8%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/gzclose.o
[ 10%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/gzlib.o
[ 12%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/gzread.o
[ 14%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/gzwrite.o
[ 15%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/inflate.o
[ 17%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/infback.o
[ 19%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/inftrees.o
[ 21%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/inffast.o
[ 22%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/trees.o
[ 24%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/uncompr.o
[ 26%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/zutil.o
[ 28%] Linking C static library ../../../lib/libz.a
[ 28%] Built target zlibstatic
Scanning dependencies of target seal_obj
[ 29%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/batchencoder.cpp.o
[ 31%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/biguint.cpp.o
[ 33%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/ciphertext.cpp.o
[ 35%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/ckks.cpp.o
[ 36%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/context.cpp.o
[ 38%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/decryptor.cpp.o
[ 40%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/intencoder.cpp.o
[ 42%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/encryptionparams.cpp.o
[ 43%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/encryptor.cpp.o
[ 45%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/evaluator.cpp.o
[ 47%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/keygenerator.cpp.o
[ 49%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/kswitchkeys.cpp.o
[ 50%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/memorymanager.cpp.o
[ 52%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/modulus.cpp.o
[ 54%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/plaintext.cpp.o
[ 56%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/randomgen.cpp.o
[ 57%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/serialization.cpp.o
[ 59%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/valcheck.cpp.o
[ 61%] Building C object CMakeFiles/seal_obj.dir/native/src/seal/util/blake2b.c.o
[ 63%] Building C object CMakeFiles/seal_obj.dir/native/src/seal/util/blake2xb.c.o
[ 64%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/clipnormal.cpp.o
[ 66%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/croots.cpp.o
[ 68%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/globals.cpp.o
[ 70%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/galois.cpp.o
[ 71%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/hash.cpp.o
[ 73%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/mempool.cpp.o
[ 75%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/numth.cpp.o
[ 77%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/polyarith.cpp.o
[ 78%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/polyarithmod.cpp.o
[ 80%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/polyarithsmallmod.cpp.o
[ 82%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/rlwe.cpp.o
[ 84%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/rns.cpp.o
[ 85%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/scalingvariant.cpp.o
[ 87%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/ntt.cpp.o
[ 89%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/streambuf.cpp.o
[ 91%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/uintarith.cpp.o
[ 92%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/uintarithmod.cpp.o
[ 94%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/uintarithsmallmod.cpp.o
[ 96%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/uintcore.cpp.o
[ 98%] Building CXX object CMakeFiles/seal_obj.dir/native/src/seal/util/ztools.cpp.o
[ 98%] Built target seal_obj
Scanning dependencies of target seal
[100%] Linking CXX static library lib/libseal-3.5.a
[100%] Built target seal
```
## Building Unit Tests and Installing

```
  cmake . -DSEAL_BUILD_TESTS=ON                                                                          28.04.20    19:42:29 
-- Build type (CMAKE_BUILD_TYPE): Release
-- Microsoft SEAL debug mode: OFF
-- Setting up MSGSL ...
-- Setting up ZLIB ...
-- Setting up Google Test ...
Cloning into 'src'...
HEAD is now at 703bd9ca Googletest export
-- Found PythonInterp: /usr/local/bin/python (found version "2.7.17")
-- Looking for C++ include x86intrin.h
-- Looking for C++ include x86intrin.h - found
-- Check size of size_t
-- Check size of size_t - done
-- Configuring done
-- Generating done
-- Build files have been written to: /Users/maverickzhn/repos/trellisfw/agapecert-osc/he/SEAL

  ~/repos/trellisfw/agapecert-osc/he/SEAL     master  v3.5.0 
   make                                                                                                   28.04.20    19:45:48 
Scanning dependencies of target gtest
[  1%] Building CXX object thirdparty/googletest/build/googletest/CMakeFiles/gtest.dir/src/gtest-all.cc.o
[  2%] Linking CXX static library ../../../../lib/libgtest.a
[  2%] Built target gtest
Scanning dependencies of target zlibstatic
[  2%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/adler32.o
[  3%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/compress.o
[  4%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/crc32.o
[  6%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/deflate.o
[  7%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/gzclose.o
[  7%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/gzlib.o
[  8%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/gzread.o
[  9%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/gzwrite.o
[ 10%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/inflate.o
[ 12%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/infback.o
[ 12%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/inftrees.o
[ 13%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/inffast.o
[ 14%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/trees.o
[ 15%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/uncompr.o
[ 16%] Building C object thirdparty/zlib/src/CMakeFiles/zlibstatic.dir/zutil.o
[ 18%] Linking C static library ../../../lib/libz.a
[ 18%] Built target zlibstatic
[ 56%] Built target seal_obj
[ 57%] Linking CXX static library lib/libseal-3.5.a
[ 57%] Built target seal
Scanning dependencies of target sealtest
[ 59%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/batchencoder.cpp.o
[ 60%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/biguint.cpp.o
[ 60%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/ciphertext.cpp.o
[ 61%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/ckks.cpp.o
[ 62%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/context.cpp.o
[ 63%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/intencoder.cpp.o
[ 65%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/encryptionparams.cpp.o
[ 65%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/encryptor.cpp.o
[ 66%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/evaluator.cpp.o
[ 67%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/galoiskeys.cpp.o
[ 68%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/intarray.cpp.o
[ 69%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/keygenerator.cpp.o
[ 71%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/memorymanager.cpp.o
[ 71%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/modulus.cpp.o
[ 72%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/plaintext.cpp.o
[ 73%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/publickey.cpp.o
[ 74%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/randomgen.cpp.o
[ 75%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/randomtostd.cpp.o
[ 75%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/relinkeys.cpp.o
[ 77%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/secretkey.cpp.o
[ 78%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/serialization.cpp.o
[ 79%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/testrunner.cpp.o
[ 80%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/clipnormal.cpp.o
[ 80%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/common.cpp.o
[ 81%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/galois.cpp.o
[ 83%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/hash.cpp.o
[ 84%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/iterator.cpp.o
[ 85%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/locks.cpp.o
[ 85%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/mempool.cpp.o
[ 86%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/numth.cpp.o
[ 87%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/polyarith.cpp.o
[ 89%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/polyarithmod.cpp.o
[ 90%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/polyarithsmallmod.cpp.o
[ 90%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/polycore.cpp.o
[ 91%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/rns.cpp.o
[ 92%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/ntt.cpp.o
[ 93%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/stringtouint64.cpp.o
[ 95%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/uint64tostring.cpp.o
[ 95%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/uintarith.cpp.o
[ 96%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/uintarithmod.cpp.o
[ 97%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/uintarithsmallmod.cpp.o
[ 98%] Building CXX object CMakeFiles/sealtest.dir/native/tests/seal/util/uintcore.cpp.o
[100%] Linking CXX executable bin/sealtest
[100%] Built target sealtest

  ~/repos/trellisfw/agapecert-osc/he/SEAL     master  v3.5.0 
   sudo make install                                                                                      28.04.20    19:55:11 
Password:
Install the project...
-- Install configuration: "Release"
-- Installing: /usr/local/lib/libseal-3.5.a
-- Installing: /usr/local/lib/cmake/SEAL-3.5/SEALTargets.cmake
-- Installing: /usr/local/lib/cmake/SEAL-3.5/SEALTargets-release.cmake
-- Installing: /usr/local/lib/cmake/SEAL-3.5/SEALConfig.cmake
-- Installing: /usr/local/lib/cmake/SEAL-3.5/SEALConfigVersion.cmake
-- Installing: /usr/local/include/SEAL-3.5/gsl
-- Installing: /usr/local/include/SEAL-3.5/gsl/gsl_util
-- Installing: /usr/local/include/SEAL-3.5/gsl/gsl_assert
-- Installing: /usr/local/include/SEAL-3.5/gsl/span
-- Installing: /usr/local/include/SEAL-3.5/gsl/gsl
-- Installing: /usr/local/include/SEAL-3.5/gsl/pointers
-- Installing: /usr/local/include/SEAL-3.5/gsl/gsl_algorithm
-- Installing: /usr/local/include/SEAL-3.5/gsl/gsl_byte
-- Installing: /usr/local/include/SEAL-3.5/gsl/multi_span
-- Installing: /usr/local/include/SEAL-3.5/gsl/string_span
-- Installing: /usr/local/include/SEAL-3.5/seal/batchencoder.h
-- Installing: /usr/local/include/SEAL-3.5/seal/biguint.h
-- Installing: /usr/local/include/SEAL-3.5/seal/ciphertext.h
-- Installing: /usr/local/include/SEAL-3.5/seal/ckks.h
-- Installing: /usr/local/include/SEAL-3.5/seal/modulus.h
-- Installing: /usr/local/include/SEAL-3.5/seal/context.h
-- Installing: /usr/local/include/SEAL-3.5/seal/decryptor.h
-- Installing: /usr/local/include/SEAL-3.5/seal/intencoder.h
-- Installing: /usr/local/include/SEAL-3.5/seal/encryptionparams.h
-- Installing: /usr/local/include/SEAL-3.5/seal/encryptor.h
-- Installing: /usr/local/include/SEAL-3.5/seal/evaluator.h
-- Installing: /usr/local/include/SEAL-3.5/seal/galoiskeys.h
-- Installing: /usr/local/include/SEAL-3.5/seal/intarray.h
-- Installing: /usr/local/include/SEAL-3.5/seal/keygenerator.h
-- Installing: /usr/local/include/SEAL-3.5/seal/kswitchkeys.h
-- Installing: /usr/local/include/SEAL-3.5/seal/memorymanager.h
-- Installing: /usr/local/include/SEAL-3.5/seal/plaintext.h
-- Installing: /usr/local/include/SEAL-3.5/seal/publickey.h
-- Installing: /usr/local/include/SEAL-3.5/seal/randomgen.h
-- Installing: /usr/local/include/SEAL-3.5/seal/randomtostd.h
-- Installing: /usr/local/include/SEAL-3.5/seal/relinkeys.h
-- Installing: /usr/local/include/SEAL-3.5/seal/seal.h
-- Installing: /usr/local/include/SEAL-3.5/seal/secretkey.h
-- Installing: /usr/local/include/SEAL-3.5/seal/serializable.h
-- Installing: /usr/local/include/SEAL-3.5/seal/serialization.h
-- Installing: /usr/local/include/SEAL-3.5/seal/valcheck.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/blake2.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/blake2-impl.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/clang.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/clipnormal.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/common.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/config.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/croots.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/defines.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/galois.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/gcc.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/globals.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/hash.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/hestdparms.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/iterator.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/locks.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/mempool.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/msvc.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/numth.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/pointer.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/polyarith.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/polyarithmod.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/polyarithsmallmod.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/polycore.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/rlwe.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/rns.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/scalingvariant.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/ntt.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/streambuf.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/uintarith.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/uintarithmod.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/uintarithsmallmod.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/uintcore.h
-- Installing: /usr/local/include/SEAL-3.5/seal/util/ztools.h
```

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

### Unit Tests

```
  bin/sealtest                                                                                           28.04.20    19:59:43 
[==========] Running 281 tests from 46 test suites.
[----------] Global test environment set-up.
[----------] 3 tests from BatchEncoderTest
[ RUN      ] BatchEncoderTest.BatchUnbatchUIntVector
[       OK ] BatchEncoderTest.BatchUnbatchUIntVector (3 ms)
[ RUN      ] BatchEncoderTest.BatchUnbatchIntVector
[       OK ] BatchEncoderTest.BatchUnbatchIntVector (3 ms)
[ RUN      ] BatchEncoderTest.BatchUnbatchPlaintext
[       OK ] BatchEncoderTest.BatchUnbatchPlaintext (2 ms)
[----------] 3 tests from BatchEncoderTest (8 ms total)

[----------] 7 tests from BigUnsignedInt
[ RUN      ] BigUnsignedInt.EmptyBigUInt
[       OK ] BigUnsignedInt.EmptyBigUInt (0 ms)
[ RUN      ] BigUnsignedInt.BigUInt64Bits
[       OK ] BigUnsignedInt.BigUInt64Bits (0 ms)
[ RUN      ] BigUnsignedInt.BigUInt99Bits
[       OK ] BigUnsignedInt.BigUInt99Bits (0 ms)
[ RUN      ] BigUnsignedInt.SaveLoadUInt
[       OK ] BigUnsignedInt.SaveLoadUInt (6 ms)
[ RUN      ] BigUnsignedInt.DuplicateTo
[       OK ] BigUnsignedInt.DuplicateTo (0 ms)
[ RUN      ] BigUnsignedInt.DuplicateFrom
[       OK ] BigUnsignedInt.DuplicateFrom (0 ms)
[ RUN      ] BigUnsignedInt.BigUIntCopyMoveAssign
[       OK ] BigUnsignedInt.BigUIntCopyMoveAssign (0 ms)
[----------] 7 tests from BigUnsignedInt (6 ms total)

[----------] 2 tests from CiphertextTest
[ RUN      ] CiphertextTest.CiphertextBasics
[       OK ] CiphertextTest.CiphertextBasics (3 ms)
[ RUN      ] CiphertextTest.SaveLoadCiphertext
[       OK ] CiphertextTest.SaveLoadCiphertext (17 ms)
[----------] 2 tests from CiphertextTest (20 ms total)

[----------] 2 tests from CKKSEncoderTest
[ RUN      ] CKKSEncoderTest.CKKSEncoderEncodeVectorDecodeTest
[       OK ] CKKSEncoderTest.CKKSEncoderEncodeVectorDecodeTest (120 ms)
[ RUN      ] CKKSEncoderTest.CKKSEncoderEncodeSingleDecodeTest
[       OK ] CKKSEncoderTest.CKKSEncoderEncodeSingleDecodeTest (39 ms)
[----------] 2 tests from CKKSEncoderTest (159 ms total)

[----------] 2 tests from ContextTest
[ RUN      ] ContextTest.ContextConstructor
[       OK ] ContextTest.ContextConstructor (176 ms)
[ RUN      ] ContextTest.ModulusChainExpansion
[       OK ] ContextTest.ModulusChainExpansion (49 ms)
[----------] 2 tests from ContextTest (226 ms total)

[----------] 1 test from EncryptionParameterQualifiersTest
[ RUN      ] EncryptionParameterQualifiersTest.ParameterError
[       OK ] EncryptionParameterQualifiersTest.ParameterError (1 ms)
[----------] 1 test from EncryptionParameterQualifiersTest (1 ms total)

[----------] 5 tests from Encoder
[ RUN      ] Encoder.IntEncodeDecodeBigUInt
[       OK ] Encoder.IntEncodeDecodeBigUInt (0 ms)
[ RUN      ] Encoder.IntEncodeDecodeUInt64
[       OK ] Encoder.IntEncodeDecodeUInt64 (0 ms)
[ RUN      ] Encoder.IntEncodeDecodeUInt32
[       OK ] Encoder.IntEncodeDecodeUInt32 (0 ms)
[ RUN      ] Encoder.IntEncodeDecodeInt64
[       OK ] Encoder.IntEncodeDecodeInt64 (0 ms)
[ RUN      ] Encoder.IntEncodeDecodeInt32
[       OK ] Encoder.IntEncodeDecodeInt32 (0 ms)
[----------] 5 tests from Encoder (0 ms total)

[----------] 3 tests from EncryptionParametersTest
[ RUN      ] EncryptionParametersTest.EncryptionParametersSet
[       OK ] EncryptionParametersTest.EncryptionParametersSet (3 ms)
[ RUN      ] EncryptionParametersTest.EncryptionParametersCompare
[       OK ] EncryptionParametersTest.EncryptionParametersCompare (2 ms)
[ RUN      ] EncryptionParametersTest.EncryptionParametersSaveLoad
[       OK ] EncryptionParametersTest.EncryptionParametersSaveLoad (7 ms)
[----------] 3 tests from EncryptionParametersTest (12 ms total)

[----------] 4 tests from EncryptorTest
[ RUN      ] EncryptorTest.BFVEncryptDecrypt
[       OK ] EncryptorTest.BFVEncryptDecrypt (63 ms)
[ RUN      ] EncryptorTest.BFVEncryptZeroDecrypt
[       OK ] EncryptorTest.BFVEncryptZeroDecrypt (19 ms)
[ RUN      ] EncryptorTest.CKKSEncryptZeroDecrypt
[       OK ] EncryptorTest.CKKSEncryptZeroDecrypt (18 ms)
[ RUN      ] EncryptorTest.CKKSEncryptDecrypt
[       OK ] EncryptorTest.CKKSEncryptDecrypt (224 ms)
[----------] 4 tests from EncryptorTest (324 ms total)

[----------] 32 tests from EvaluatorTest
[ RUN      ] EvaluatorTest.BFVEncryptNegateDecrypt
[       OK ] EvaluatorTest.BFVEncryptNegateDecrypt (6 ms)
[ RUN      ] EvaluatorTest.BFVEncryptAddDecrypt
[       OK ] EvaluatorTest.BFVEncryptAddDecrypt (10 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptAddDecrypt
[       OK ] EvaluatorTest.CKKSEncryptAddDecrypt (242 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptAddPlainDecrypt
[       OK ] EvaluatorTest.CKKSEncryptAddPlainDecrypt (121 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptSubPlainDecrypt
[       OK ] EvaluatorTest.CKKSEncryptSubPlainDecrypt (146 ms)
[ RUN      ] EvaluatorTest.BFVEncryptSubDecrypt
[       OK ] EvaluatorTest.BFVEncryptSubDecrypt (9 ms)
[ RUN      ] EvaluatorTest.BFVEncryptAddPlainDecrypt
[       OK ] EvaluatorTest.BFVEncryptAddPlainDecrypt (6 ms)
[ RUN      ] EvaluatorTest.BFVEncryptSubPlainDecrypt
[       OK ] EvaluatorTest.BFVEncryptSubPlainDecrypt (7 ms)
[ RUN      ] EvaluatorTest.BFVEncryptMultiplyPlainDecrypt
[       OK ] EvaluatorTest.BFVEncryptMultiplyPlainDecrypt (31 ms)
[ RUN      ] EvaluatorTest.BFVEncryptMultiplyDecrypt
[       OK ] EvaluatorTest.BFVEncryptMultiplyDecrypt (82 ms)
[ RUN      ] EvaluatorTest.BFVRelinearize
[       OK ] EvaluatorTest.BFVRelinearize (37 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptNaiveMultiplyDecrypt
[       OK ] EvaluatorTest.CKKSEncryptNaiveMultiplyDecrypt (258 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptMultiplyByNumberDecrypt
[       OK ] EvaluatorTest.CKKSEncryptMultiplyByNumberDecrypt (150 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptMultiplyRelinDecrypt
[       OK ] EvaluatorTest.CKKSEncryptMultiplyRelinDecrypt (202 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptSquareRelinDecrypt
[       OK ] EvaluatorTest.CKKSEncryptSquareRelinDecrypt (224 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptMultiplyRelinRescaleDecrypt
[       OK ] EvaluatorTest.CKKSEncryptMultiplyRelinRescaleDecrypt (825 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptSquareRelinRescaleDecrypt
[       OK ] EvaluatorTest.CKKSEncryptSquareRelinRescaleDecrypt (191 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptModSwitchDecrypt
[       OK ] EvaluatorTest.CKKSEncryptModSwitchDecrypt (288 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptMultiplyRelinRescaleModSwitchAddDecrypt
[       OK ] EvaluatorTest.CKKSEncryptMultiplyRelinRescaleModSwitchAddDecrypt (429 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptRotateDecrypt
[       OK ] EvaluatorTest.CKKSEncryptRotateDecrypt (66 ms)
[ RUN      ] EvaluatorTest.CKKSEncryptRescaleRotateDecrypt
[       OK ] EvaluatorTest.CKKSEncryptRescaleRotateDecrypt (92 ms)
[ RUN      ] EvaluatorTest.BFVEncryptSquareDecrypt
[       OK ] EvaluatorTest.BFVEncryptSquareDecrypt (19 ms)
[ RUN      ] EvaluatorTest.BFVEncryptMultiplyManyDecrypt
[       OK ] EvaluatorTest.BFVEncryptMultiplyManyDecrypt (28 ms)
[ RUN      ] EvaluatorTest.BFVEncryptExponentiateDecrypt
[       OK ] EvaluatorTest.BFVEncryptExponentiateDecrypt (22 ms)
[ RUN      ] EvaluatorTest.BFVEncryptAddManyDecrypt
[       OK ] EvaluatorTest.BFVEncryptAddManyDecrypt (21 ms)
[ RUN      ] EvaluatorTest.TransformPlainToNTT
[       OK ] EvaluatorTest.TransformPlainToNTT (11 ms)
[ RUN      ] EvaluatorTest.TransformEncryptedToFromNTT
[       OK ] EvaluatorTest.TransformEncryptedToFromNTT (10 ms)
[ RUN      ] EvaluatorTest.BFVEncryptMultiplyPlainNTTDecrypt
[       OK ] EvaluatorTest.BFVEncryptMultiplyPlainNTTDecrypt (12 ms)
[ RUN      ] EvaluatorTest.BFVEncryptApplyGaloisDecrypt
[       OK ] EvaluatorTest.BFVEncryptApplyGaloisDecrypt (20 ms)
[ RUN      ] EvaluatorTest.BFVEncryptRotateMatrixDecrypt
[       OK ] EvaluatorTest.BFVEncryptRotateMatrixDecrypt (19 ms)
[ RUN      ] EvaluatorTest.BFVEncryptModSwitchToNextDecrypt
[       OK ] EvaluatorTest.BFVEncryptModSwitchToNextDecrypt (22 ms)
[ RUN      ] EvaluatorTest.BFVEncryptModSwitchToDecrypt
[       OK ] EvaluatorTest.BFVEncryptModSwitchToDecrypt (30 ms)
[----------] 32 tests from EvaluatorTest (3636 ms total)

[----------] 2 tests from GaloisKeysTest
[ RUN      ] GaloisKeysTest.GaloisKeysSaveLoad
[       OK ] GaloisKeysTest.GaloisKeysSaveLoad (81 ms)
[ RUN      ] GaloisKeysTest.GaloisKeysSeededSaveLoad
[       OK ] GaloisKeysTest.GaloisKeysSeededSaveLoad (68 ms)
[----------] 2 tests from GaloisKeysTest (151 ms total)

[----------] 3 tests from IntArrayTest
[ RUN      ] IntArrayTest.IntArrayBasics
[       OK ] IntArrayTest.IntArrayBasics (0 ms)
[ RUN      ] IntArrayTest.SaveLoadIntArray
[       OK ] IntArrayTest.SaveLoadIntArray (3 ms)
[ RUN      ] IntArrayTest.Assign
[       OK ] IntArrayTest.Assign (0 ms)
[----------] 3 tests from IntArrayTest (3 ms total)

[----------] 3 tests from KeyGeneratorTest
[ RUN      ] KeyGeneratorTest.BFVKeyGeneration
[       OK ] KeyGeneratorTest.BFVKeyGeneration (127 ms)
[ RUN      ] KeyGeneratorTest.CKKSKeyGeneration
[       OK ] KeyGeneratorTest.CKKSKeyGeneration (125 ms)
[ RUN      ] KeyGeneratorTest.Constructors
[       OK ] KeyGeneratorTest.Constructors (90 ms)
[----------] 3 tests from KeyGeneratorTest (342 ms total)

[----------] 3 tests from MemoryPoolHandleTest
[ RUN      ] MemoryPoolHandleTest.MemoryPoolHandleConstructAssign
[       OK ] MemoryPoolHandleTest.MemoryPoolHandleConstructAssign (0 ms)
[ RUN      ] MemoryPoolHandleTest.MemoryPoolHandleAllocate
[       OK ] MemoryPoolHandleTest.MemoryPoolHandleAllocate (0 ms)
[ RUN      ] MemoryPoolHandleTest.UseCount
[       OK ] MemoryPoolHandleTest.UseCount (0 ms)
[----------] 3 tests from MemoryPoolHandleTest (0 ms total)

[----------] 3 tests from ModulusTest
[ RUN      ] ModulusTest.CreateModulus
[       OK ] ModulusTest.CreateModulus (0 ms)
[ RUN      ] ModulusTest.CompareModulus
[       OK ] ModulusTest.CompareModulus (0 ms)
[ RUN      ] ModulusTest.SaveLoadModulus
[       OK ] ModulusTest.SaveLoadModulus (7 ms)
[----------] 3 tests from ModulusTest (7 ms total)

[----------] 2 tests from CoeffModTest
[ RUN      ] CoeffModTest.CustomExceptionTest
[       OK ] CoeffModTest.CustomExceptionTest (0 ms)
[ RUN      ] CoeffModTest.CustomTest
[       OK ] CoeffModTest.CustomTest (2 ms)
[----------] 2 tests from CoeffModTest (2 ms total)

[----------] 2 tests from PlaintextTest
[ RUN      ] PlaintextTest.PlaintextBasics
[       OK ] PlaintextTest.PlaintextBasics (0 ms)
[ RUN      ] PlaintextTest.SaveLoadPlaintext
[       OK ] PlaintextTest.SaveLoadPlaintext (22 ms)
[----------] 2 tests from PlaintextTest (22 ms total)

[----------] 1 test from PublicKeyTest
[ RUN      ] PublicKeyTest.SaveLoadPublicKey
[       OK ] PublicKeyTest.SaveLoadPublicKey (20 ms)
[----------] 1 test from PublicKeyTest (20 ms total)

[----------] 6 tests from RandomGenerator
[ RUN      ] RandomGenerator.UniformRandomCreateDefault
[       OK ] RandomGenerator.UniformRandomCreateDefault (0 ms)
[ RUN      ] RandomGenerator.SequentialRandomGenerator
[       OK ] RandomGenerator.SequentialRandomGenerator (0 ms)
[ RUN      ] RandomGenerator.RandomUInt64
[       OK ] RandomGenerator.RandomUInt64 (4 ms)
[ RUN      ] RandomGenerator.SeededRNG
[       OK ] RandomGenerator.SeededRNG (0 ms)
[ RUN      ] RandomGenerator.RandomSeededRNG
[       OK ] RandomGenerator.RandomSeededRNG (1 ms)
[ RUN      ] RandomGenerator.MultiThreaded
[       OK ] RandomGenerator.MultiThreaded (1 ms)
[----------] 6 tests from RandomGenerator (7 ms total)

[----------] 1 test from RandomToStandard
[ RUN      ] RandomToStandard.RandomToStandardGenerate
[       OK ] RandomToStandard.RandomToStandardGenerate (0 ms)
[----------] 1 test from RandomToStandard (0 ms total)

[----------] 2 tests from RelinKeysTest
[ RUN      ] RelinKeysTest.RelinKeysSaveLoad
[       OK ] RelinKeysTest.RelinKeysSaveLoad (28 ms)
[ RUN      ] RelinKeysTest.RelinKeysSeededSaveLoad
[       OK ] RelinKeysTest.RelinKeysSeededSaveLoad (21 ms)
[----------] 2 tests from RelinKeysTest (49 ms total)

[----------] 1 test from SecretKeyTest
[ RUN      ] SecretKeyTest.SaveLoadSecretKey
[       OK ] SecretKeyTest.SaveLoadSecretKey (15 ms)
[----------] 1 test from SecretKeyTest (16 ms total)

[----------] 5 tests from SerializationTest
[ RUN      ] SerializationTest.IsValidHeader
[       OK ] SerializationTest.IsValidHeader (0 ms)
[ RUN      ] SerializationTest.SEALHeaderSaveLoad
[       OK ] SerializationTest.SEALHeaderSaveLoad (0 ms)
[ RUN      ] SerializationTest.SEALHeaderUpgrade
[       OK ] SerializationTest.SEALHeaderUpgrade (0 ms)
[ RUN      ] SerializationTest.SaveLoadToStream
[       OK ] SerializationTest.SaveLoadToStream (1 ms)
[ RUN      ] SerializationTest.SaveLoadToBuffer
[       OK ] SerializationTest.SaveLoadToBuffer (4 ms)
[----------] 5 tests from SerializationTest (6 ms total)

[----------] 1 test from ClipNormal
[ RUN      ] ClipNormal.ClipNormalGenerate
[       OK ] ClipNormal.ClipNormalGenerate (1 ms)
[----------] 1 test from ClipNormal (1 ms total)

[----------] 10 tests from Common
[ RUN      ] Common.Constants
[       OK ] Common.Constants (0 ms)
[ RUN      ] Common.UnsignedComparisons
[       OK ] Common.UnsignedComparisons (0 ms)
[ RUN      ] Common.SafeArithmetic
[       OK ] Common.SafeArithmetic (0 ms)
[ RUN      ] Common.FitsIn
[       OK ] Common.FitsIn (0 ms)
[ RUN      ] Common.DivideRoundUp
[       OK ] Common.DivideRoundUp (0 ms)
[ RUN      ] Common.GetUInt64Byte
[       OK ] Common.GetUInt64Byte (0 ms)
[ RUN      ] Common.ReverseBits32
[       OK ] Common.ReverseBits32 (0 ms)
[ RUN      ] Common.ReverseBits64
[       OK ] Common.ReverseBits64 (0 ms)
[ RUN      ] Common.GetSignificantBitCount
[       OK ] Common.GetSignificantBitCount (0 ms)
[ RUN      ] Common.GetMSBIndexGeneric
[       OK ] Common.GetMSBIndexGeneric (0 ms)
[----------] 10 tests from Common (15 ms total)

[----------] 7 tests from GaloisToolTest
[ RUN      ] GaloisToolTest.Create
[       OK ] GaloisToolTest.Create (7 ms)
[ RUN      ] GaloisToolTest.EltFromStep
[       OK ] GaloisToolTest.EltFromStep (0 ms)
[ RUN      ] GaloisToolTest.EltsFromSteps
[       OK ] GaloisToolTest.EltsFromSteps (0 ms)
[ RUN      ] GaloisToolTest.EltsAll
[       OK ] GaloisToolTest.EltsAll (0 ms)
[ RUN      ] GaloisToolTest.IndexFromElt
[       OK ] GaloisToolTest.IndexFromElt (0 ms)
[ RUN      ] GaloisToolTest.ApplyGalois
[       OK ] GaloisToolTest.ApplyGalois (4 ms)
[ RUN      ] GaloisToolTest.ApplyGaloisNTT
[       OK ] GaloisToolTest.ApplyGaloisNTT (2 ms)
[----------] 7 tests from GaloisToolTest (13 ms total)

[----------] 1 test from HashTest
[ RUN      ] HashTest.Hash
[       OK ] HashTest.Hash (0 ms)
[----------] 1 test from HashTest (0 ms total)

[----------] 6 tests from IteratorTest
[ RUN      ] IteratorTest.CoeffIter
[       OK ] IteratorTest.CoeffIter (0 ms)
[ RUN      ] IteratorTest.RNSIter
[       OK ] IteratorTest.RNSIter (0 ms)
[ RUN      ] IteratorTest.PolyIter
[       OK ] IteratorTest.PolyIter (0 ms)
[ RUN      ] IteratorTest.PtrIter
[       OK ] IteratorTest.PtrIter (0 ms)
[ RUN      ] IteratorTest.ReverseIter
[       OK ] IteratorTest.ReverseIter (0 ms)
[ RUN      ] IteratorTest.IterTuple
[       OK ] IteratorTest.IterTuple (0 ms)
[----------] 6 tests from IteratorTest (0 ms total)

[----------] 2 tests from ReaderWriterLockerTests
[ RUN      ] ReaderWriterLockerTests.ReaderWriterLockNonBlocking
[       OK ] ReaderWriterLockerTests.ReaderWriterLockNonBlocking (0 ms)
[ RUN      ] ReaderWriterLockerTests.ReaderWriterLockBlocking
[       OK ] ReaderWriterLockerTests.ReaderWriterLockBlocking (21 ms)
[----------] 2 tests from ReaderWriterLockerTests (21 ms total)

[----------] 1 test from MemoryPoolTest
[ RUN      ] MemoryPoolTest.TestMemoryPoolMT
[       OK ] MemoryPoolTest.TestMemoryPoolMT (0 ms)
[----------] 1 test from MemoryPoolTest (0 ms total)

[----------] 6 tests from MemoryPoolTests
[ RUN      ] MemoryPoolTests.PointerTestsMT
[       OK ] MemoryPoolTests.PointerTestsMT (0 ms)
[ RUN      ] MemoryPoolTests.DuplicateIfNeededMT
[       OK ] MemoryPoolTests.DuplicateIfNeededMT (0 ms)
[ RUN      ] MemoryPoolTests.TestMemoryPoolST
[       OK ] MemoryPoolTests.TestMemoryPoolST (0 ms)
[ RUN      ] MemoryPoolTests.PointerTestsST
[       OK ] MemoryPoolTests.PointerTestsST (0 ms)
[ RUN      ] MemoryPoolTests.DuplicateIfNeededST
[       OK ] MemoryPoolTests.DuplicateIfNeededST (0 ms)
[ RUN      ] MemoryPoolTests.Allocate
[       OK ] MemoryPoolTests.Allocate (0 ms)
[----------] 6 tests from MemoryPoolTests (1 ms total)

[----------] 8 tests from NumberTheory
[ RUN      ] NumberTheory.GCD
[       OK ] NumberTheory.GCD (0 ms)
[ RUN      ] NumberTheory.ExtendedGCD
[       OK ] NumberTheory.ExtendedGCD (0 ms)
[ RUN      ] NumberTheory.TryInvertUIntMod
[       OK ] NumberTheory.TryInvertUIntMod (0 ms)
[ RUN      ] NumberTheory.IsPrime
[       OK ] NumberTheory.IsPrime (2 ms)
[ RUN      ] NumberTheory.NAF
[       OK ] NumberTheory.NAF (0 ms)
[ RUN      ] NumberTheory.TryPrimitiveRootMod
[       OK ] NumberTheory.TryPrimitiveRootMod (1 ms)
[ RUN      ] NumberTheory.IsPrimitiveRootMod
[       OK ] NumberTheory.IsPrimitiveRootMod (0 ms)
[ RUN      ] NumberTheory.TryMinimalPrimitiveRootMod
[       OK ] NumberTheory.TryMinimalPrimitiveRootMod (1 ms)
[----------] 8 tests from NumberTheory (5 ms total)

[----------] 8 tests from PolyArith
[ RUN      ] PolyArith.RightShiftPolyCoeffs
[       OK ] PolyArith.RightShiftPolyCoeffs (0 ms)
[ RUN      ] PolyArith.NegatePoly
[       OK ] PolyArith.NegatePoly (0 ms)
[ RUN      ] PolyArith.AddPolyPoly
[       OK ] PolyArith.AddPolyPoly (0 ms)
[ RUN      ] PolyArith.SubPolyPoly
[       OK ] PolyArith.SubPolyPoly (0 ms)
[ RUN      ] PolyArith.MultiplyPolyPoly
[       OK ] PolyArith.MultiplyPolyPoly (0 ms)
[ RUN      ] PolyArith.PolyInftyNorm
[       OK ] PolyArith.PolyInftyNorm (0 ms)
[ RUN      ] PolyArith.PolyEvalPoly
[       OK ] PolyArith.PolyEvalPoly (0 ms)
[ RUN      ] PolyArith.ExponentiatePoly
[       OK ] PolyArith.ExponentiatePoly (0 ms)
[----------] 8 tests from PolyArith (0 ms total)

[----------] 3 tests from PolyArithMod
[ RUN      ] PolyArithMod.NegatePolyCoeffMod
[       OK ] PolyArithMod.NegatePolyCoeffMod (0 ms)
[ RUN      ] PolyArithMod.AddPolyPolyCoeffMod
[       OK ] PolyArithMod.AddPolyPolyCoeffMod (0 ms)
[ RUN      ] PolyArithMod.SubPolyPolyCoeffMod
[       OK ] PolyArithMod.SubPolyPolyCoeffMod (0 ms)
[----------] 3 tests from PolyArithMod (0 ms total)

[----------] 12 tests from PolyArithSmallMod
[ RUN      ] PolyArithSmallMod.SmallModuloPolyCoeffs
[       OK ] PolyArithSmallMod.SmallModuloPolyCoeffs (0 ms)
[ RUN      ] PolyArithSmallMod.NegatePolyCoeffSmallMod
[       OK ] PolyArithSmallMod.NegatePolyCoeffSmallMod (0 ms)
[ RUN      ] PolyArithSmallMod.AddPolyPolyCoeffSmallMod
[       OK ] PolyArithSmallMod.AddPolyPolyCoeffSmallMod (0 ms)
[ RUN      ] PolyArithSmallMod.SubPolyPolyCoeffSmallMod
[       OK ] PolyArithSmallMod.SubPolyPolyCoeffSmallMod (0 ms)
[ RUN      ] PolyArithSmallMod.MultiplyPolyScalarCoeffSmallMod
[       OK ] PolyArithSmallMod.MultiplyPolyScalarCoeffSmallMod (0 ms)
[ RUN      ] PolyArithSmallMod.MultiplyPolyMonoCoeffSmallMod
[       OK ] PolyArithSmallMod.MultiplyPolyMonoCoeffSmallMod (0 ms)
[ RUN      ] PolyArithSmallMod.MultiplyPolyPolyCoeffSmallMod
[       OK ] PolyArithSmallMod.MultiplyPolyPolyCoeffSmallMod (0 ms)
[ RUN      ] PolyArithSmallMod.DividePolyPolyCoeffSmallMod
[       OK ] PolyArithSmallMod.DividePolyPolyCoeffSmallMod (0 ms)
[ RUN      ] PolyArithSmallMod.DyadicProductCoeffSmallMod
[       OK ] PolyArithSmallMod.DyadicProductCoeffSmallMod (0 ms)
[ RUN      ] PolyArithSmallMod.TryInvertPolyCoeffSmallMod
[       OK ] PolyArithSmallMod.TryInvertPolyCoeffSmallMod (0 ms)
[ RUN      ] PolyArithSmallMod.PolyInftyNormCoeffSmallMod
[       OK ] PolyArithSmallMod.PolyInftyNormCoeffSmallMod (0 ms)
[ RUN      ] PolyArithSmallMod.NegacyclicShiftPolyCoeffSmallMod
[       OK ] PolyArithSmallMod.NegacyclicShiftPolyCoeffSmallMod (0 ms)
[----------] 12 tests from PolyArithSmallMod (18 ms total)

[----------] 11 tests from PolyCore
[ RUN      ] PolyCore.AllocatePoly
[       OK ] PolyCore.AllocatePoly (0 ms)
[ RUN      ] PolyCore.SetZeroPoly
[       OK ] PolyCore.SetZeroPoly (0 ms)
[ RUN      ] PolyCore.AllocateZeroPoly
[       OK ] PolyCore.AllocateZeroPoly (0 ms)
[ RUN      ] PolyCore.GetPolyCoeff
[       OK ] PolyCore.GetPolyCoeff (0 ms)
[ RUN      ] PolyCore.SetPolyPoly
[       OK ] PolyCore.SetPolyPoly (0 ms)
[ RUN      ] PolyCore.IsZeroPoly
[       OK ] PolyCore.IsZeroPoly (0 ms)
[ RUN      ] PolyCore.IsEqualPolyPoly
[       OK ] PolyCore.IsEqualPolyPoly (0 ms)
[ RUN      ] PolyCore.IsOneZeroOnePoly
[       OK ] PolyCore.IsOneZeroOnePoly (0 ms)
[ RUN      ] PolyCore.GetSignificantCoeffCountPoly
[       OK ] PolyCore.GetSignificantCoeffCountPoly (0 ms)
[ RUN      ] PolyCore.DuplicatePolyIfNeeded
[       OK ] PolyCore.DuplicatePolyIfNeeded (0 ms)
[ RUN      ] PolyCore.ArePolyCoeffsLessThan
[       OK ] PolyCore.ArePolyCoeffsLessThan (0 ms)
[----------] 11 tests from PolyCore (1 ms total)

[----------] 8 tests from RNSBaseTest
[ RUN      ] RNSBaseTest.Create
[       OK ] RNSBaseTest.Create (1 ms)
[ RUN      ] RNSBaseTest.ArrayAccess
[       OK ] RNSBaseTest.ArrayAccess (0 ms)
[ RUN      ] RNSBaseTest.Copy
[       OK ] RNSBaseTest.Copy (0 ms)
[ RUN      ] RNSBaseTest.Contains
[       OK ] RNSBaseTest.Contains (0 ms)
[ RUN      ] RNSBaseTest.IsSubbaseOf
[       OK ] RNSBaseTest.IsSubbaseOf (1 ms)
[ RUN      ] RNSBaseTest.Extend
[       OK ] RNSBaseTest.Extend (1 ms)
[ RUN      ] RNSBaseTest.Drop
[       OK ] RNSBaseTest.Drop (0 ms)
[ RUN      ] RNSBaseTest.ComposeDecompose
[       OK ] RNSBaseTest.ComposeDecompose (3 ms)
[----------] 8 tests from RNSBaseTest (6 ms total)

[----------] 3 tests from BaseConvToolTest
[ RUN      ] BaseConvToolTest.Initialize
[       OK ] BaseConvToolTest.Initialize (0 ms)
[ RUN      ] BaseConvToolTest.Convert
[       OK ] BaseConvToolTest.Convert (0 ms)
[ RUN      ] BaseConvToolTest.ConvertArray
[       OK ] BaseConvToolTest.ConvertArray (0 ms)
[----------] 3 tests from BaseConvToolTest (0 ms total)

[----------] 8 tests from RNSToolTest
[ RUN      ] RNSToolTest.Initialize
[       OK ] RNSToolTest.Initialize (7 ms)
[ RUN      ] RNSToolTest.FastBConvMTilde
[       OK ] RNSToolTest.FastBConvMTilde (3 ms)
[ RUN      ] RNSToolTest.MontgomeryReduction
[       OK ] RNSToolTest.MontgomeryReduction (4 ms)
[ RUN      ] RNSToolTest.FastFloor
[       OK ] RNSToolTest.FastFloor (4 ms)
[ RUN      ] RNSToolTest.FastBConvSK
[       OK ] RNSToolTest.FastBConvSK (4 ms)
[ RUN      ] RNSToolTest.ExactScaleAndRound
[       OK ] RNSToolTest.ExactScaleAndRound (3 ms)
[ RUN      ] RNSToolTest.DivideAndRoundQLastInplace
[       OK ] RNSToolTest.DivideAndRoundQLastInplace (5 ms)
[ RUN      ] RNSToolTest.DivideAndRoundQLastNTTInplace
[       OK ] RNSToolTest.DivideAndRoundQLastNTTInplace (2 ms)
[----------] 8 tests from RNSToolTest (36 ms total)

[----------] 4 tests from NTTTablesTest
[ RUN      ] NTTTablesTest.NTTBasics
[       OK ] NTTTablesTest.NTTBasics (10 ms)
[ RUN      ] NTTTablesTest.NTTPrimitiveRootsTest
[       OK ] NTTTablesTest.NTTPrimitiveRootsTest (0 ms)
[ RUN      ] NTTTablesTest.NegacyclicNTTTest
[       OK ] NTTTablesTest.NegacyclicNTTTest (1 ms)
[ RUN      ] NTTTablesTest.InverseNegacyclicNTTTest
[       OK ] NTTTablesTest.InverseNegacyclicNTTTest (2 ms)
[----------] 4 tests from NTTTablesTest (13 ms total)

[----------] 4 tests from StringToUInt64
[ RUN      ] StringToUInt64.IsHexCharTest
[       OK ] StringToUInt64.IsHexCharTest (0 ms)
[ RUN      ] StringToUInt64.HexToNibbleTest
[       OK ] StringToUInt64.HexToNibbleTest (0 ms)
[ RUN      ] StringToUInt64.GetHexStringBitCount
[       OK ] StringToUInt64.GetHexStringBitCount (0 ms)
[ RUN      ] StringToUInt64.HexStringToUInt64
[       OK ] StringToUInt64.HexStringToUInt64 (0 ms)
[----------] 4 tests from StringToUInt64 (0 ms total)

[----------] 4 tests from UInt64ToString
[ RUN      ] UInt64ToString.NibbleToUpperHexTest
[       OK ] UInt64ToString.NibbleToUpperHexTest (0 ms)
[ RUN      ] UInt64ToString.UInt64ToHexString
[       OK ] UInt64ToString.UInt64ToHexString (0 ms)
[ RUN      ] UInt64ToString.UInt64ToDecString
[       OK ] UInt64ToString.UInt64ToDecString (0 ms)
[ RUN      ] UInt64ToString.PolyToHexString
[       OK ] UInt64ToString.PolyToHexString (0 ms)
[----------] 4 tests from UInt64ToString (0 ms total)

[----------] 36 tests from UIntArith
[ RUN      ] UIntArith.AddUInt64Generic
[       OK ] UIntArith.AddUInt64Generic (0 ms)
[ RUN      ] UIntArith.AddUInt64
[       OK ] UIntArith.AddUInt64 (0 ms)
[ RUN      ] UIntArith.SubUInt64Generic
[       OK ] UIntArith.SubUInt64Generic (0 ms)
[ RUN      ] UIntArith.SubUInt64
[       OK ] UIntArith.SubUInt64 (0 ms)
[ RUN      ] UIntArith.AddUInt128
[       OK ] UIntArith.AddUInt128 (0 ms)
[ RUN      ] UIntArith.AddUIntUInt
[       OK ] UIntArith.AddUIntUInt (0 ms)
[ RUN      ] UIntArith.SubUIntUInt
[       OK ] UIntArith.SubUIntUInt (0 ms)
[ RUN      ] UIntArith.AddUIntUInt64
[       OK ] UIntArith.AddUIntUInt64 (0 ms)
[ RUN      ] UIntArith.SubUIntUInt64
[       OK ] UIntArith.SubUIntUInt64 (0 ms)
[ RUN      ] UIntArith.IncrementUInt
[       OK ] UIntArith.IncrementUInt (0 ms)
[ RUN      ] UIntArith.DecrementUInt
[       OK ] UIntArith.DecrementUInt (0 ms)
[ RUN      ] UIntArith.NegateUInt
[       OK ] UIntArith.NegateUInt (0 ms)
[ RUN      ] UIntArith.LeftShiftUInt
[       OK ] UIntArith.LeftShiftUInt (0 ms)
[ RUN      ] UIntArith.LeftShiftUInt128
[       OK ] UIntArith.LeftShiftUInt128 (0 ms)
[ RUN      ] UIntArith.LeftShiftUInt192
[       OK ] UIntArith.LeftShiftUInt192 (0 ms)
[ RUN      ] UIntArith.RightShiftUInt
[       OK ] UIntArith.RightShiftUInt (0 ms)
[ RUN      ] UIntArith.RightShiftUInt128
[       OK ] UIntArith.RightShiftUInt128 (0 ms)
[ RUN      ] UIntArith.RightShiftUInt192
[       OK ] UIntArith.RightShiftUInt192 (0 ms)
[ RUN      ] UIntArith.HalfRoundUpUInt
[       OK ] UIntArith.HalfRoundUpUInt (0 ms)
[ RUN      ] UIntArith.NotUInt
[       OK ] UIntArith.NotUInt (0 ms)
[ RUN      ] UIntArith.AndUIntUInt
[       OK ] UIntArith.AndUIntUInt (0 ms)
[ RUN      ] UIntArith.OrUIntUInt
[       OK ] UIntArith.OrUIntUInt (0 ms)
[ RUN      ] UIntArith.XorUIntUInt
[       OK ] UIntArith.XorUIntUInt (0 ms)
[ RUN      ] UIntArith.MultiplyUInt64Generic
[       OK ] UIntArith.MultiplyUInt64Generic (0 ms)
[ RUN      ] UIntArith.MultiplyUInt64
[       OK ] UIntArith.MultiplyUInt64 (0 ms)
[ RUN      ] UIntArith.MultiplyUInt64HW64Generic
[       OK ] UIntArith.MultiplyUInt64HW64Generic (0 ms)
[ RUN      ] UIntArith.MultiplyUInt64HW64
[       OK ] UIntArith.MultiplyUInt64HW64 (0 ms)
[ RUN      ] UIntArith.MultiplyManyUInt64
[       OK ] UIntArith.MultiplyManyUInt64 (0 ms)
[ RUN      ] UIntArith.MultiplyManyUInt64Except
[       OK ] UIntArith.MultiplyManyUInt64Except (0 ms)
[ RUN      ] UIntArith.MultiplyUIntUInt
[       OK ] UIntArith.MultiplyUIntUInt (1 ms)
[ RUN      ] UIntArith.MultiplyUIntUInt64
[       OK ] UIntArith.MultiplyUIntUInt64 (0 ms)
[ RUN      ] UIntArith.DivideUIntUInt
[       OK ] UIntArith.DivideUIntUInt (0 ms)
[ RUN      ] UIntArith.DivideUInt128UInt64
[       OK ] UIntArith.DivideUInt128UInt64 (0 ms)
[ RUN      ] UIntArith.DivideUInt192UInt64
[       OK ] UIntArith.DivideUInt192UInt64 (0 ms)
[ RUN      ] UIntArith.ExponentiateUInt
[       OK ] UIntArith.ExponentiateUInt (0 ms)
[ RUN      ] UIntArith.ExponentiateUInt64
[       OK ] UIntArith.ExponentiateUInt64 (0 ms)
[----------] 36 tests from UIntArith (3 ms total)

[----------] 7 tests from UIntArithMod
[ RUN      ] UIntArithMod.IncrementUIntMod
[       OK ] UIntArithMod.IncrementUIntMod (0 ms)
[ RUN      ] UIntArithMod.DecrementUIntMod
[       OK ] UIntArithMod.DecrementUIntMod (0 ms)
[ RUN      ] UIntArithMod.NegateUIntMod
[       OK ] UIntArithMod.NegateUIntMod (0 ms)
[ RUN      ] UIntArithMod.Div2UIntMod
[       OK ] UIntArithMod.Div2UIntMod (0 ms)
[ RUN      ] UIntArithMod.AddUIntUIntMod
[       OK ] UIntArithMod.AddUIntUIntMod (0 ms)
[ RUN      ] UIntArithMod.SubUIntUIntMod
[       OK ] UIntArithMod.SubUIntUIntMod (0 ms)
[ RUN      ] UIntArithMod.TryInvertUIntMod
[       OK ] UIntArithMod.TryInvertUIntMod (0 ms)
[----------] 7 tests from UIntArithMod (0 ms total)

[----------] 13 tests from UIntArithSmallMod
[ RUN      ] UIntArithSmallMod.IncrementUIntMod
[       OK ] UIntArithSmallMod.IncrementUIntMod (1 ms)
[ RUN      ] UIntArithSmallMod.DecrementUIntMod
[       OK ] UIntArithSmallMod.DecrementUIntMod (0 ms)
[ RUN      ] UIntArithSmallMod.NegateUIntMod
[       OK ] UIntArithSmallMod.NegateUIntMod (1 ms)
[ RUN      ] UIntArithSmallMod.Div2UIntMod
[       OK ] UIntArithSmallMod.Div2UIntMod (0 ms)
[ RUN      ] UIntArithSmallMod.AddUIntMod
[       OK ] UIntArithSmallMod.AddUIntMod (0 ms)
[ RUN      ] UIntArithSmallMod.SubUIntMod
[       OK ] UIntArithSmallMod.SubUIntMod (1 ms)
[ RUN      ] UIntArithSmallMod.BarrettReduce128
[       OK ] UIntArithSmallMod.BarrettReduce128 (0 ms)
[ RUN      ] UIntArithSmallMod.MultiplyUIntUIntMod
[       OK ] UIntArithSmallMod.MultiplyUIntUIntMod (0 ms)
[ RUN      ] UIntArithSmallMod.MultiplyAddMod
[       OK ] UIntArithSmallMod.MultiplyAddMod (0 ms)
[ RUN      ] UIntArithSmallMod.ModuloUIntMod
[       OK ] UIntArithSmallMod.ModuloUIntMod (1 ms)
[ RUN      ] UIntArithSmallMod.TryInvertUIntMod
[       OK ] UIntArithSmallMod.TryInvertUIntMod (0 ms)
[ RUN      ] UIntArithSmallMod.ExponentiateUIntMod
[       OK ] UIntArithSmallMod.ExponentiateUIntMod (0 ms)
[ RUN      ] UIntArithSmallMod.DotProductMod
[       OK ] UIntArithSmallMod.DotProductMod (0 ms)
[----------] 13 tests from UIntArithSmallMod (4 ms total)

[----------] 23 tests from UIntCore
[ RUN      ] UIntCore.AllocateUInt
[       OK ] UIntCore.AllocateUInt (0 ms)
[ RUN      ] UIntCore.SetZeroUInt
[       OK ] UIntCore.SetZeroUInt (0 ms)
[ RUN      ] UIntCore.AllocateZeroUInt
[       OK ] UIntCore.AllocateZeroUInt (0 ms)
[ RUN      ] UIntCore.SetUInt
[       OK ] UIntCore.SetUInt (0 ms)
[ RUN      ] UIntCore.SetUIntUInt
[       OK ] UIntCore.SetUIntUInt (1 ms)
[ RUN      ] UIntCore.SetUIntUInt2
[       OK ] UIntCore.SetUIntUInt2 (0 ms)
[ RUN      ] UIntCore.IsZeroUInt
[       OK ] UIntCore.IsZeroUInt (0 ms)
[ RUN      ] UIntCore.IsEqualUInt
[       OK ] UIntCore.IsEqualUInt (0 ms)
[ RUN      ] UIntCore.IsBitSetUInt
[       OK ] UIntCore.IsBitSetUInt (0 ms)
[ RUN      ] UIntCore.IsHighBitSetUInt
[       OK ] UIntCore.IsHighBitSetUInt (0 ms)
[ RUN      ] UIntCore.SetBitUInt
[       OK ] UIntCore.SetBitUInt (0 ms)
[ RUN      ] UIntCore.GetSignificantBitCountUInt
[       OK ] UIntCore.GetSignificantBitCountUInt (0 ms)
[ RUN      ] UIntCore.GetSignificantUInt64CountUInt
[       OK ] UIntCore.GetSignificantUInt64CountUInt (0 ms)
[ RUN      ] UIntCore.GetNonzeroUInt64CountUInt
[       OK ] UIntCore.GetNonzeroUInt64CountUInt (0 ms)
[ RUN      ] UIntCore.GetPowerOfTwoUInt
[       OK ] UIntCore.GetPowerOfTwoUInt (0 ms)
[ RUN      ] UIntCore.GetPowerOfTwoMinusOneUInt
[       OK ] UIntCore.GetPowerOfTwoMinusOneUInt (0 ms)
[ RUN      ] UIntCore.FilterHighBitsUInt
[       OK ] UIntCore.FilterHighBitsUInt (0 ms)
[ RUN      ] UIntCore.CompareUIntUInt
[       OK ] UIntCore.CompareUIntUInt (0 ms)
[ RUN      ] UIntCore.GetPowerOfTwo
[       OK ] UIntCore.GetPowerOfTwo (0 ms)
[ RUN      ] UIntCore.GetPowerOfTwoMinusOne
[       OK ] UIntCore.GetPowerOfTwoMinusOne (0 ms)
[ RUN      ] UIntCore.DuplicateUIntIfNeeded
[       OK ] UIntCore.DuplicateUIntIfNeeded (0 ms)
[ RUN      ] UIntCore.HammingWeight
[       OK ] UIntCore.HammingWeight (0 ms)
[ RUN      ] UIntCore.HammingWeightSplit
[       OK ] UIntCore.HammingWeightSplit (0 ms)
[----------] 23 tests from UIntCore (2 ms total)

[----------] Global test environment tear-down
[==========] 281 tests from 46 test suites ran. (5178 ms total)
[  PASSED  ] 281 tests.
```

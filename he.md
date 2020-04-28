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


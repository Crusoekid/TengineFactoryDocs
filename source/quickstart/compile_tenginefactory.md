# Build TengineFactory

## Environmental requirements
- opencv >= 3.4
- cmake >= 3.10
- protobuf >= 3.0
- gcc >= 4.9
- ndk >= 15c （If Use Android）

## Build Linux version
1. clone [TengineFactory](https://github.com/OAID/TengineFactory) project，`git clone https://github.com/OAID/TengineFactory.git`
2. build dynamic library.
```bash
./build.sh
```
The directory structure after compilation is as follows:
```Text
TengineFactory
├── build
│   └── libTFactory.so
└── include
    └── TFactoryComponent.hpp
    └── TFactoryProcess.hpp
```

## Build Androidv7/v8 version
Download ndk, [http://developer.android.com/ndk/downloads/index.html](http://developer.android.com/ndk/downloads/index.html)
(Optional) Delete the debug parameter to reduce the binary size. The file android.toolchain.cmake can be found from $ANDROID_NDK/build/cmake.
```bash
# vim $ANDROID_NDK/build/cmake/android.toolchain.cmake
# delete "-g" line
list(APPEND ANDROID_COMPILER_FLAGS
  -g
  -DANDROID
```

Configuration Environment:
```bash
export $ANDROID_NDK=<NDK-path>
```

Android v7 build command:
```bash
mkdir build-android-armv7
cd build-android-armv7
cmake -DCMAKE_TOOLCHAIN_FILE=$ANDROID_NDK/build/cmake/android.toolchain.cmake -DANDROID_ABI="armeabi-v7a" -DANDROID_ARM_NEON=ON -DANDROID_PLATFORM=android-19 ..
make
```

Android v8 build command：
```bash
mkdir build-android-aarch64
cd build-android-aarch64
cmake -DCMAKE_TOOLCHAIN_FILE=$ANDROID_NDK/build-android-aarch64/cmake/android.toolchain.cmake -DANDROID_ABI="arm64-v8a" -DANDROID_PLATFORM=android-21 ..
make
```
# Controller #

An attempt to create an application that can communicate with a hub to allow for remote control / sending of scripts / sensor logging without needing any of the LEGO apps.

## Android ##

So far just a skeleton of a native app that draws to the screen. To build it you will need both the android sdk and ndk.

```shell
cd controller-android
mkdir BUILD
cd BUILD
cmake \
    -DCMAKE_BUILD_TYPE=Debug \
    -DCMAKE_TOOLCHAIN_FILE=${ANDROID_NDK_ROOT}/build/cmake/android.toolchain.cmake \
    -DANDROID_SDK=${ANDROID_SDK_ROOT} \
    -DANDROID_NDK=${ANDROID_NDK_ROOT} \
    -DANDROID_PLATFORM=android-21 \
    -DANDROID_STL=c++_static \
    -DJAVA_HOME=${JAVA_HOME} \
    ..
    
cmake --build . --target apk
```

To install and launch the app on a connected device using adb you can use this target:

```shell
cmake --build . --target apk-deploy
```

## Desktop ##

TODO...

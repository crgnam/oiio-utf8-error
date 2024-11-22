OpenImageIO Issue Example

This project is meant to reproduce the build failure experienced on MSVC when using OpenImageIO.

In Visual Studio with vcpkg already cloned/integrated, simply clone the project and build it.  It should fail with:

```
C:<foo>\out\build\x64-Release\vcpkg_installed\x64-windows\include\OpenImageIO\detail\fmt\base.h(458): error C2338: static_assert failed: 'Unicode support requires compiling with /utf-8'
```

I do not get the issue when compiling with g++ (Ubuntu 11.4.0-1ubuntu1~22.04) 11.4.0, which I do using the following commands:

```
mkdir build;
cd build;
cmake ../ -DCMAKE_BUILD_TYPE=Release -DCMAKE_TOOLCHAIN_FILE=<path/to/my/vcpkg>/scripts/buildsystems/vcpkg.cmake
cmake --build .
```
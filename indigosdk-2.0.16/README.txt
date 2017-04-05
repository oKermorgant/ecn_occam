
==========================================================================================
== Visual Studio 2015 compilation

cd <base SDK directory>
mkdir build
cd build
del CMakeCache.txt && cmake -G "Visual Studio 14 2015" -DOpenCV_DIR=e:/opencv/build -DUSE_OPENCV=1 -DUSE_OPENGL=0 -DINDIGOSDK_MSVC_STATIC_CRT=OFF ..
cmake --build . --config Release -- /nologo /v:m

==========================================================================================
== Ubuntu compilation

On Ubuntu, if you configure with OpenGL support you'll need to install X11 and GL related libs, as well as libxxf86vm-dev.

## build with OpenCV and OpenGL support
mkdir -p release && cd -p release
rm -f CMakeCache.txt && cmake -DOpenCV_DIR=~/opencv/build -DUSE_OPENCV=1 -DUSE_OPENGL=1 ..

## build with OpenGL support but no OpenCV support
mkdir -p release && cd -p release
rm -f CMakeCache.txt && cmake -DUSE_OPENCV=0 -DUSE_OPENGL=1 ..

## build with neither OpenCV nor OpenGL support
mkdir -p release && cd -p release
rm -f CMakeCache.txt && cmake -DUSE_OPENCV=0 -DUSE_OPENGL=0 ..


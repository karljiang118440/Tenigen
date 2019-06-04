#一、环境搭建方法
##1.1、

1、
 sudo apt install libprotobuf-dev protobuf-compiler libboost-all-dev libgoogle-glog-dev
 sudo apt install libopencv-dev\
2、
cd ~/tengine
cp makefile.config.example makefile.config



3、

./build/tests/bin/bench_sqz -1

4、

cd examples/mobilenet_ssd


##2、出现的问题
1、

/usr/bin/ld: cannot find -lopenblas” error in Caffe compilation

>apt install liblapack-dev liblapack3 libopenblas-base libopenblas-dev


2、

/media/jcq/study/Tengine/Tengine-master/examples/mobilenet_ssd/MSSD
proto file not specified,using /media/jcq/study/Tengine/Tengine-master/models/MobileNetSSD_deploy.prototxt by default
model file not specified,using /media/jcq/study/Tengine/Tengine-master/models/MobileNetSSD_deploy.caffemodel by default
image file not specified,using /media/jcq/study/Tengine/Tengine-master/tests/images/ssd_dog.jpg by default
Input file not existed: /media/jcq/study/Tengine/Tengine-master/models/MobileNetSSD_deploy.prototxt

修改配置：

##3、execute results：

save.jpg 成功 ，文件位于 /media/jcq/study/Tengine/Tengine-master/examples/mobilenet_ssd


# 二、ARm Platform builds
##1、makefile.configure modifications
1、#CONFIG_ARCH_ARM64=y  >  CONFIG_ARCH_ARM64=y
2、# CROSS_COMPILE=aarch64-linux-gnu- > CROSS_COMPILE=aarch64-linux-gnu-
3、# cross compile for ARM64  > cross compile for ARM64



##2、cmakelist modifications

1、option(CONFIG_ARCH_ARM64 "build arm64 version" OFF) > option(CONFIG_ARCH_ARM64 "build arm64 version" ON) 
2、option(CONFIG_ARCH_ARM8_2 "build float16 for arm8.2" OFF) to option(CONFIG_ARCH_ARM8_2 "build float16 for arm8.2" ON)


##3、makefile midifications 
1、 aarch64 path changes:

ifeq ($(CROSS_COMPILE),aarch64-linux-gnu-)
   SYSROOT_FLAGS:=--sysroot=$(SYSROOT) 
   SYSROOT_LDFLAGS:=-L/usr/lib/aarch64-linux-gnu -L/lib/aarch64-linux-gnu
   PKG_CONFIG_PATH:=$(SYSROOT)/usr/lib/aarch64-linux-gnu/pkgconfig
   export PKG_CONFIG_PATH
endif

2、add aarch64-linux-gnu  path

sudo gedit ~/.bashrc

export PATH=/media/jcq/study/CrossTools/gcc-linaro-4.9-2016.02-x86_64_aarch64-linux-gnu/aarch64-linux-gnu/bin:$PATH

aarch64-linux-gnu-gcc --version












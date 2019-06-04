#一、jcq 编译器问题
     出现问题无法继续编译，原先能够编译的都失败了，先到虚拟机中重新编译。
     
     > 编译的选项问题，涉及编译的内容太多。恢复之前 make.config 重新编译。
     
     
#二、虚拟机中编译 Tengine_GPU.md

##1、computelibrary build ，三个指令都确定下来。
ACL_ROOT=/home/djiango/NEON/ComputeLibrary-master

##2、编译器指定
export PATH＝$PATH:/home/djiango/bsp15.0/gcc-linaro-4.9-2016.02-x86_64_aarch64-linux-gnu/bin



#三、编译debug

##1、
error: missing binary operator before token "("
 #if __GLIBC_PREREQ(2,15) && defined(_GNU_SOURCE)



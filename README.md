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

##3、执行结果：




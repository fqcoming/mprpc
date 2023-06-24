### mprpc

Mprpc is developed based on Muduo high-performance network library and Protobuf.


#### 1.build and run

Tested on:
    unbuntu 20.04 and unbuntu 22.04

Install required packages:
  # ubuntu
  $ sudo apt install g++ cmake make libboost-dev



### 1.1 boost

```shell
$ sudo apt-get install libboost-dev
```


# muduo

```shell
sudo apt install zlib1g-dev
git clone https://github.com/chenshuo/muduo.git
cd muduo
mkdir build
cd build
cmake ../cmake
make
sudo make install
```


# protobuf
# 选择安装石磊老师课程给的安装包
# 在ubuntu22上编译报错，换到ubuntu20上就顺利编译成功了。可能与gcc编译器版本有关
# 原因是在ubuntu22上没有安装build-essensial 
# 因此，在ubuntu20和22都能安装成功

```shell
$ sudo apt-get install gcc g++
$ sudo apt-get install libtool
$ sudo apt-get install autoconf
$ sudo apt install build-essensial cmake make 
$ sudo apt install unzip
$ unzip protobuf-master.zip
$ cd protobuf-master
$ sudo apt-get install autoconf automake libtool curl make
$ ./autogen.sh
$ ./configure
$ make
$ sudo make install
$ sudo ldconfig  # 刷新动态库
$ protoc --version  # libprotoc 3.11.0
$ protoc test.proto --cpp_out=./     # 编译proto文件命令
$ g++ -o main main.cc test.pb.cc -lprotobuf
```


ZooKeeper

```shell
tar -xzf zookeeper-3.4.10.tar.gz 
```

关于zookeeper编译报错
https://blog.csdn.net/weixin_43604792/article/details/103879578
https://www.bbsmax.com/A/gVdnNooEdW/

















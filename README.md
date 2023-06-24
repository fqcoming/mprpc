### mprpc

Mprpc is developed based on Muduo high-performance network library and Protobuf.


#### 1.build and run

Tested on:
    unbuntu 20.04 and unbuntu 22.04

Install required packages:


```shell
sudo apt-get install gcc g++ make cmake build-essential
```


boost + muduo

```shell
sudo apt-get install libboost-dev
sudo apt install zlib1g-dev
git clone https://github.com/chenshuo/muduo.git  # Alternatively, manually download and unzip the file
cd muduo
mkdir build
cd build
cmake .. && make
sudo make install
```



protobuf

https://github.com/protocolbuffers/protobuf
Directly manually downloaded version 3.19.4

```shell
sudo apt install unzip
unzip protobuf-3.19.4.zip
cd protobuf-3.19.4
sudo apt-get install autoconf automake libtool curl make
./autogen.sh
./configure
make
sudo make install
sudo ldconfig  # Refresh Dynamic Library
protoc --version  # libprotoc 3.19.4
```


```shell
protoc test.proto --cpp_out=./     # Compile *.proto file command
g++ -o main main.cc test.pb.cc -lprotobuf   # 
```


ZooKeeper

```shell
tar -xzf zookeeper-3.4.10.tar.gz
cd zookeeper-3.4.10/src/c
sudo ./configure
sudo make  
```

> Make compilation error in the native C API interface of Zookeeper during Linux installation
> see also https://blog.csdn.net/weixin_43604792/article/details/103879578

```shell
sudo make
sudo make install
```

> error while loading shared libraries: reasons and solutions for errors 
> There are two reasons:
>　　1.操作系统没有改共享库
>　　2.安装了该共享库，但是执行外部程序调用该共享库的时候，程序按照默认路径（/usr/lib、/lib）找不到该共享库文件
> 解决方法：
>　　ubuntu 系统的共享库一般安装在 /usr/local/lib 目录下，如果不确定，可以使用 ls  /usr/local/lib 查看里面是否有你需要的库文件
>　　然后打开/etc/ld.so.conf，在文件最后添加/usr/local/lib（或者在命令行输入echo "/usr/local/lib" >> sudo /etc/ld.so.conf）
>　　保存退出，执行ldconfig命令即可。


















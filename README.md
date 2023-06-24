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


```shell
sudo apt install unzip
unzip protobuf-3.19.4.zip # directly manually downloaded version 3.19.4
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

Make compilation error in the native C API interface of Zookeeper during Linux installation
see also https://blog.csdn.net/weixin_43604792/article/details/103879578

```shell
sudo make
sudo make install
```

Error while loading shared libraries: reasons and solutions for errors.
The shared library has been installed, but when an external program calls the shared library, 
the program cannot find the shared library file according to the default path (/usr/lib, /lib).
The shared libraries of the Ubuntu system are usually installed in the /usr/local/lib directory. 
If unsure, you can use the following to check if there are any library files you need.

```shell
ls /usr/local/lib
```

Then open /etc/ld.so.conf and add /usr/local/lib at the end of the file (or enter the following at the command line). 

```shell
echo "/usr/local/lib" > sudo/etc/ld.so.conf
```

Save and exit, execute the ldconfig command.

```shell
ldconfig
```



















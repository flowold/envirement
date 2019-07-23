这里涉及到gflags的安装，原来使用 sudo apt-get install libgflags-dev 
但是后面有人在环境中下载安装了libgflags的安装包，解压后直接安装： 

mkdir build 
cd build 
cmake .. 
make 
make test 
make install 

网上很多博客都这样写，其实这是错误的安装方法，这种只能得到静态库。 
gflags 正确的安装方法是这样的： 
Need cmake >2.8.4 (current is 2.8.3)

mkdir build 
cd build 
cmake -DCMAKE_INSTALL_PREFIX=/usr/local -DBUILD_SHARED_LIBS=ON -DGFLAGS_NAMESPACE=google -G "Unix Makefiles" ../ 
make
sudo make install 
sudo ldconfig 

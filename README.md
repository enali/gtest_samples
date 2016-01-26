# GTest Examples

`GTest`是广泛应用的谷歌的C++单元测试框架.此处是随源码发行的示例.只是添加了`CMakeLists.txt`文件,用于演示如何在`cmake`中使用`GTest`.源文件目前没有注释,最好自己去看原仓库的示例代码.

官方仓库: [GTest](https://github.com/google/googletest)

## Install

* `git clone https://github.com/google/googletest`
* `cd googletest && mkdir build && cd build`
* `cmake .. && make`
* `sudo make install`

会将生成的静态库`libgtest.a`, `libgtest_main.a`, `libgmock.a`,`libgmock_main.a`
安装到`/usr/local/lib`中,将头文件安装到`/usr/local/include/gtest/`中.

默认安装的`/usr/local/lib`不在`cmake`模块的查找范围,建议手动复制到`/usr/lib`中.

## Ubuntu

`Ubuntu`官方仓库提供有`GTest`的源文件包.

`sudo apt-get install libgtest-dev`, 会相对`Github`低一个小版本.

在`/usr/src/gtest`中保存有源代码,需要在其中自己编译生成静态库, 再自己复制到`/usr/lib`中.

## Usage

* 克隆此仓库
* `$ cd gtest_examples && mkdir build && cd build`
* `$ cmake .. && make`
* `$ make test`或`ctest`

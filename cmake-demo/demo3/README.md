# 多个目录,多个源文件
1. 目录结构如下:
./demo3
    |
    +--- main.cpp
    |
    +--- math/
          |
          +--- MathFunctions.cpp
          |
          +--- MathFunctions.h

2. 简单点的话,Cmake文件可以在demo1工程目录上修改为:
```shell
# 指定生成目标, 这里有几个cpp就全列举
add_executable(Demo main.cpp MathFunctions.cpp)
```
3. 最好的方法是使用aux_source_directory(xxx)
4. 注意: 编译的时候,先编译math中的,也正常生成个build目录,再cmake make命令
此时会生成一个.a类似于压缩包
然后再到main.cpp同级目录下,生成个build目录,再cmake make编译,就会正常生成
可执行文件了
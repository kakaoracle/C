# 单个目录,两个源文件+一个头文件
1. 目录结构如下:
./Demo2
    |
    +--- main.cc
    |
    +--- MathFunctions.cc
    |
    +--- MathFunctions.h
2. 简单点的话,Cmake文件可以在demo1工程目录上修改为:
```shell
# 指定生成目标, 这里有几个cpp就全列举
add_executable(Demo main.cpp MathFunctions.cpp)
```
3. 最好的方法是使用aux_source_directory(xxx)
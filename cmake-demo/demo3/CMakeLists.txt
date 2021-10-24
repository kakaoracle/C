# CMake 最低版本号要求
cmake_minimum_required (VERSION 3.20)

# 项目信息
project (kaka3)

# 查找当前目录下的所有源文件
# 并将名称保存到 DIR_SRCS 变量
aux_source_directory(. DIR_SRCS)

#添加math子目录
add_subdirectory(math)
# 指定生成目标
add_executable(kakademo3 main.cpp)

# 添加链接库,此处第二个入参是子目录中cmakelist文件中的输出名
target_link_libraries(kakademo3 MathFunctions)
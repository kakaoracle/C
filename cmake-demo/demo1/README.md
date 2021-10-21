# 单源文件
1. 初始状态,只有两个文件,main.cpp与CmakeLists.txt
2. 其余的比如CmakeFiles目录及其他文件都是后续命令生成的
3. 执行cmake . 命令,就会生成第二步的很多杂乱的文件
4. 执行make命令,就会生成bat可执行文件
5. ./Demo 5 4就会走程序逻辑
# 忽略输出的缓存文件
1. add_executable(Demo main.cpp)命令中,第一个只能是输出的文件名,无法指定目录,带的来结果就是可能大量无关文件生成在当前目录,而且可执行文件也无法添加到.gitignore
2. 因此普遍做法是外部构建(能最大程度保证目录结构的整洁):
```shell
mkdir build
cd ./build
cmake ../
make
```
外部构建后,就可以直接在.gitignore中使用build/来屏蔽整个build目录下的文件了
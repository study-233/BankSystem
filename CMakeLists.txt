# CMake 最低版本号要求
cmake_minimum_required(VERSION 3.5)  
# 项目名称
project(BANK)

#向工程添加多个特定的头文件搜索路径,路径之间用空格分隔
include_directories(include)

#添加 src 子目录 
add_subdirectory(src)

# 指定生成目标 将名为 main.cpp 的源文件编译成一个名称为 ${PROJECT_NAME} 的可执行文件,即exe文件。
add_executable(${PROJECT_NAME} main.cpp)   
#指定生成可执行文件的目录   PROJECT_BINARY_DIR 运行cmake命令的目录,通常是${PROJECT_SOURCE_DIR}/build   
SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)

# 添加链接库  可执行文件 ${PROJECT_NAME} 需要连接一个名为 Lib 的链接库 
target_link_libraries(${PROJECT_NAME} LIB_SRCS)


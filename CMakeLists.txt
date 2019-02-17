cmake_minimum_required(VERSION 3.5)
project(drivers) # 工程名字，随你怎么叫都行

include(kernel_config.cmake)  # 一堆的 add_definitions(xxx)，就不细说了
#add_definitions(-D__KERNEL__=1)


set(MY_ANDROID_ROOT_DIR "xxx") # 定义一个变量，方便后面使用
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=c99 -nostdinc") # C 编译器设置

add_executable("drivers" main.c) # dummy target，没有这个的话external libraries就是空的，
                                 # 弄一个main.c糊弄糊弄Clion

include_directories(
    "include"
    "arch/arm/include"
    "arch/arm64/include"
    # 下面这些随便你自己写吧，想看哪些代码就写哪些
    "mm"
    "drivers"
    "arch/arm"
    "arch/arm64")


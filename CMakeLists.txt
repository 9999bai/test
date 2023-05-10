cmake_minimum_required(VERSION 3.20)
project(iot_gateway)


# add_definitions("-std=c++11")

include_directories("/usr/include/mymuduo")#muduo头文件
link_directories("/usr/lib/mymuduo")#muduo库文件

include_directories("/usr/include/mysql-arm")#mysql头文件
link_directories("/usr/lib/mysql-arm")#mysql库文件

include_directories("/usr/include/json-arm/")#json头文件
link_directories("/usr/lib/json-arm/")#json库文件

include_directories("/usr/include/openssl-arm")#openssl头文件
link_directories("/usr/lib/openssl-arm")#openssl库文件

include_directories("/usr/include/mosquitto-arm")#mqtt头文件
link_directories("/usr/lib/mosquitto-arm")#mqtt库文件

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)

#静态库
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_LIST_DIR}/lib)
# 可执行文件
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_LIST_DIR}/bin)
#动态库
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_LIST_DIR}/bin)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS}  -std=c++11 -pthread -fPIC")

add_subdirectory(src)
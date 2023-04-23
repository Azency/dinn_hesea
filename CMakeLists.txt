cmake_minimum_required(VERSION 3.9)
project(demo)
 
 

# set(CMAKE_CXX_STANDARD 11)
set(CMAKE_BUILD_TYPE "Debug")
 
#! 设定源码列表.cpp
set(SOURCE_FILES ./nn_multi_pke.cpp)
aux_source_directory(${CMAKE_SOURCE_DIR}/libtfhe DIR)  


#add_executable(hello_world ${DIR})

include_directories(/home/azency/usr/local/include)
include_directories(/home/azency/usr/local/include/palisade)
include_directories(/home/azency/usr/local/include/palisade/pke)
include_directories(/home/azency/usr/local/include/palisade/core)
include_directories(/home/azency/usr/local/include/palisade/binfhe)
include_directories(/home/azency/usr/local/include/palisade/cereal)


add_executable(demo  ${SOURCE_FILES} ${DIR})

 
target_link_libraries(demo  
/home/azency/usr/local/lib/libHESEApke.so
/home/azency/usr/local/lib/libHESEAcore.so
/home/azency/usr/local/lib/libHESEAbinfhe.so)
 
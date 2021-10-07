cmake_minimum_required(VERSION 3.18.4)

project(DolphinDB-Wrapper)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS "-DLINUX -D_GLIBCXX_USE_CXX11_ABI=0")

link_directories(bin)
include_directories(include)

add_library(DolphinDB-Wrapper SHARED src/wrapper.cpp)
target_link_libraries(DolphinDB-Wrapper DolphinDBAPI 
    /usr/local/lib/openssl/lib/libssl.so.1.0.0
    /usr/local/lib/openssl/lib/libcrypto.so.1.0.0
    pthread 
    uuid)
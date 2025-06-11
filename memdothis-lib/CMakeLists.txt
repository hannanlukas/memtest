cmake_minimum_required(VERSION 3.10)
project(memdothis)

add_library(memdothis STATIC
    src/memdothis.cpp
)

target_include_directories(memdothis PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)

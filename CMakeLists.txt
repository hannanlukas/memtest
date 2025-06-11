cmake_minimum_required(VERSION 3.10)
project(memdothis)

add_library(memdothis STATIC
    src/memdothis.cpp
)

target_include_directories(memdothis PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)

include(GNUInstallDirs)

install(TARGETS memdothis
    EXPORT memdothisTargets
    ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
)

install(DIRECTORY include/
    DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
)

install(EXPORT memdothisTargets
    FILE memdothisTargets.cmake
    NAMESPACE memdothis::
    DESTINATION ${CMAKE_INSTALL_LIBDIR}/cmake/memdothis
)
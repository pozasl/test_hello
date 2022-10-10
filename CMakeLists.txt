cmake_minimum_required(VERSION 3.16)
project(hello VERSION 0.1.0 LANGUAGES C CXX)

add_executable(hello hello.cpp)

include(GNUInstallDirs)
install(TARGETS hello
        RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})
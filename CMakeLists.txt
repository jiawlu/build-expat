cmake_minimum_required(VERSION 3.25)
project(hello VERSION 1.0.0 LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(CMAKE_TOOLCHAIN_FILE "${CMAKE_SOURCE_DIR}/vcpkg/scripts/buildsystems/vcpkg.cmake")

set(CMAKE_PREFIX_PATH "${CMAKE_PREFIX_PATH};${CMAKE_SOURCE_DIR}/vcpkg/installed/x64-windows")

find_package(EXPAT MODULE REQUIRED)
set(Required_Libraries ${Required_Libraries} EXPAT::EXPAT)

add_executable(hello main.cpp)
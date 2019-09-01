cmake_minimum_required(VERSION 3.4)

project(hello)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib ${CMAKE_CURRENT_BINARY_DIR}/formatter_ex)

add_executable(hello hello_world.cpp)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)

target_link_libraries(hello formatter_ex)

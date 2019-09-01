cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(CI_try)

add_library(formatter STATIC ${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib/formatter.cpp)
add_library(formatter_ex STATIC ${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib/formatter_ex.cpp)
add_library(solverlib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/solver_lib/solver.cpp)
add_executable(hello ${CMAKE_CURRENT_SOURCE_DIR}/hello_world_application/hello_world.cpp)
add_executable(solver_app ${CMAKE_CURRENT_SOURCE_DIR}/solver_application/equation.cpp)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/solver_lib)

target_link_libraries(formatter_ex formatter)
target_link_libraries(hello formatter_ex)
target_link_libraries(solver_app formatter_ex solverlib)
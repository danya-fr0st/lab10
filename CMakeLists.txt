cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 11)
include(cmake/HunterGate.cmake)

HunterGate(
    URL "https://github.com/danya-fr0st/hunter/archive/v0.19.137.1.tar.gz"
    SHA1 "0b0770d2fd432acc9de795bca80e721f15bdbd20"
)

project(demo)

hunter_add_package(print)
find_package(print)
add_executable(demo ${CMAKE_CURRENT_SOURCE_DIR}/sources/demo.cpp)
target_link_libraries(demo print)

install(TARGETS demo RUNTIME DESTINATION bin)

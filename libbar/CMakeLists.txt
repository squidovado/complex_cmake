cmake_minimum_required(VERSION 3.14)
project(bar)
include(FetchContent)
FetchContent_Declare(foo SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/../libfoo)
FetchContent_MakeAvailable(foo)
add_library(bar STATIC bar.cpp)
target_include_directories(bar PUBLIC ${foo_SOURCE_DIR})
target_link_libraries(bar foo)

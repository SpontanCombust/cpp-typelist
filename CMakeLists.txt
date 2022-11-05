CMAKE_MINIMUM_REQUIRED(VERSION 3.1)
PROJECT(typelist)
SET(CMAKE_CXX_STANDARD 14)

option(TYPELIST_BUILD_TESTS "Build test programs" OFF)

# INTERFACE LIBRARY TARGET
add_library(typelist INTERFACE)
target_include_directories(typelist INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})

if(TYPELIST_BUILD_TESTS)
    add_executable(typelist_run_tests tests.cpp)
    target_link_libraries(typelist_run_tests typelist)
endif()

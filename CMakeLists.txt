CMAKE_MINIMUM_REQUIRED(VERSION 3.1)
PROJECT(typelist)

SET(CMAKE_CXX_STANDARD 14)


# INTERFACE LIBRARY TARGET
add_library(typelist INTERFACE)
target_include_directories(typelist INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})


# TESTS TARGET
SET(SOURCES
    typelist.hpp
    tests.cpp)

add_executable(run_tests ${SOURCES})
target_link_libraries(run_tests typelist)


ADD_CUSTOM_TARGET(format
    COMMAND clang-format -style=file -i ${SOURCES}
    WORKING_DIRECTORY ${CMAKE_SOURCE_DIR})

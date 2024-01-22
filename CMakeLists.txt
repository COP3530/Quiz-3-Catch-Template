cmake_minimum_required(VERSION 3.22)
project(Quiz3)

set(CMAKE_CXX_STANDARD 14)

#compile flags to match Gradescope test environment
set(GCC_COVERAGE_COMPILE_FLAGS "-Wall -Werror")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${GCC_COVERAGE_COMPILE_FLAGS}" )

include_directories(src)

add_executable(Tests
        src/interquartile_range.h
        test/test.cpp # your test file
        test/catch/catch_amalgamated.hpp
        test/catch/catch_amalgamated.cpp
        )
        
# comment everything below out if you are using CLion
include(CTest)
include(Catch)
catch_discover_tests(Tests) # must be named the same as your test executable

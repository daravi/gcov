cmake_minimum_required(VERSION 3.5)
project(Hello)
add_definitions("-std=c++17")
include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
SET(CXXFLAGS="-g -O0 -Wall -W -Wshadow -Wunused-variable \
 -Wunused-parameter -Wunused-function -Wunused -Wno-system-headers \
 -Wno-deprecated -Woverloaded-virtual -Wwrite-strings -fprofile-arcs -ftest-coverage")
SET(CFLAGS="-g -O0 -Wall -W -fprofile-arcs -ftest-coverage")
SET(LDFLAGS="-fprofile-arcs -ftest-coverage")
conan_basic_setup()
add_executable(hello_test hello_test.cpp)
target_link_libraries(hello_test ${CONAN_LIBS})

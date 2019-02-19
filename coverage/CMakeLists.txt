cmake_minimum_required(VERSION 3.5)

project(Coverage)
ENABLE_TESTING()

SET(CMAKE_CXX_FLAGS="-g -O0 -Wall -W  -fprofile-arcs -ftest-coverage")

SET(CMAKE_C_FLAGS="-g -O0 -Wall -W -fprofile-arcs -ftest-coverage")

#SET(CMAKE_SHARED_LINKER_FLAGS="-fprofile-arcs -ftest-coverage")
SET(CMAKE_EXE_LINKER_FLAGS="-fprofile-arcs -ftest-coverage")

add_executable(Coverage coverage.cpp)
# include_directories("/usr/local/Cellar//gcc/8.2.0/lib/gcc/8/gcc/x86_64-apple-darwin17.7.0/8.2.0/include/")
# link_directories("/usr/local/Cellar//gcc/8.2.0/lib/gcc/8/gcc/x86_64-apple-darwin17.7.0/8.2.0/")
# target_link_libraries(Coverage gcov)
target_link_libraries(Coverage /usr/local/Cellar//gcc/8.2.0/lib/gcc/8/gcc/x86_64-apple-darwin17.7.0/8.2.0/libgcov.a)

add_test(NAME Coverage COMMAND Coverage)

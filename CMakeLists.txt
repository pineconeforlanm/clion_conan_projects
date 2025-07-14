cmake_minimum_required(VERSION 4.1)
project(test_conan)

set(CMAKE_CXX_STANDARD 23)

add_subdirectory(boost)
add_subdirectory(grpc)
add_subdirectory(logger)
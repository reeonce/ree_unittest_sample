cmake_minimum_required(VERSION 3.0.0 FATAL_ERROR)

project(ree_unittest_sample CXX)

if(NOT TARGET ree_unittest)
    add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../ree_unittest
        ${CMAKE_CURRENT_BINARY_DIR}/ree_unittest)
endif(NOT TARGET ree_unittest)

add_executable(ree_unittest_sample main.cc hello_world_test.cc)
target_link_libraries(ree_unittest_sample PRIVATE ree_unittest)

set_target_properties(ree_unittest_sample PROPERTIES
    CMAKE_CXX_STANDARD 11
    CMAKE_CXX_STANDARD_REQUIRED ON
    CMAKE_CXX_EXTENSIONS OFF
)
cmake_minimum_required(VERSION 2.8.7)

project(caches)

set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR}/lib)

set(CACHE_INCLUDE_DIRS ${caches_SOURCE_DIR}/include CACHE INTERNAL "")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

option(BUILD_TEST "Build tests for the project" ON)

if (${BUILD_TEST})
  enable_testing()
endif()

add_subdirectory(deps)
add_subdirectory(src)

if (${BUILD_TEST})
  add_subdirectory(test)
endif()

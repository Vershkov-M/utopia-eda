# SPDX-License-Identifier: Apache-2.0

cmake_minimum_required(VERSION 3.13)

project(Utopia VERSION 0.0)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

include_directories(SYSTEM lib/lorina/include)
include_directories(SYSTEM lib/lorina/lib/fmt)

set(Cudd_ROOT $ENV{CUDD_DIR})

find_package(Cudd REQUIRED)
find_package(Yosys REQUIRED)

add_subdirectory(lib)
add_subdirectory(src)
add_subdirectory(test)

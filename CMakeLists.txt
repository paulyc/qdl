# Copyright (C) 2019 Paul Ciarlo <paul.ciarlo@gmail.com>
# Licensed under the terms of the 3-Clause BSD License; see LICENSE

cmake_minimum_required (VERSION 3.11)
project (qdl)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O2 -Wall -g")

find_library(UDEV_LIBRARY udev)
find_package(libxml2 REQUIRED)
include_directories(${LIBXML2_INCLUDE_DIRS})

add_executable(qdl firehose.c qdl.c sahara.c util.c patch.c program.c ufs.c)
target_link_libraries(qdl ${UDEV_LIBRARY} ${LIBXML2_LIBRARIES})

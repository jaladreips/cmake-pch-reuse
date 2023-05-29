cmake_minimum_required(VERSION 3.16)

project(PCH LANGUAGES CXX)

set(dummyPCHFile "pch.cpp")
file(GENERATE 
     OUTPUT ${dummyPCHFile}
     CONTENT ""
)
add_library(PCH STATIC ${dummyPCHFile})

target_precompile_headers(PCH
    PRIVATE
    "${CMAKE_SOURCE_DIR}/PCH/pch.h"
)
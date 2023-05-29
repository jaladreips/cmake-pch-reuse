cmake_minimum_required(VERSION 3.16)

project(PCH LANGUAGES CXX)

# add_executable(PCH pch.cpp)
set(dummyPCHFile "pch.cpp")
file(GENERATE 
     OUTPUT ${dummyPCHFile}
     CONTENT ""
)
add_library(PCH STATIC ${dummyPCHFile})
# add_library(PCH INTERFACE)
# target_include_directories(PCH INTERFACE .)
# target_sources(PCH INTERFACE ${CMAKE_CURRENT_LIST_DIR}/pch.h)
# set_property(TARGET PCH PROPERTY ENABLE_EXPORTS 1)

target_precompile_headers(PCH
    PRIVATE
    "${CMAKE_SOURCE_DIR}/PCH/pch.h"
)
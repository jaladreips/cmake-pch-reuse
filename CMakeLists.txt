cmake_minimum_required(VERSION 3.16)

add_subdirectory("PCH")

project(MAIN1)

add_executable(MAIN1
main.cpp
)

target_precompile_headers(MAIN1 REUSE_FROM PCH)

project(MAIN2)

add_executable(MAIN2
main.cpp
)

target_precompile_headers(MAIN2 REUSE_FROM PCH)

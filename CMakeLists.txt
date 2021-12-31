cmake_minimum_required(VERSION 3.16)
project(drat_trim C)

set(CMAKE_C_STANDARD 99)

add_executable(drat-trim drat-trim.c)
add_executable(lrat-check lrat-check.c)
add_executable(compress compress.c)
add_executable(decompress decompress.c)
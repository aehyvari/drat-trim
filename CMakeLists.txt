cmake_minimum_required(VERSION 3.16)

if (POLICY CMP0074) # Policy 0074 has been introduced in CMake 3.12, so we need a check, otherwise older version would give an error
    cmake_policy(SET CMP0074 NEW)
endif()

set(PROOFCHECK_VERSION_MAJOR 0)
set(PROOFCHECK_VERSION_MINOR 0)
set(PROOFCHECK_VERSION_PATCH 0)
set(PROOFCHECK_VERSION ${PROOFCHECK_VERSION_MAJOR}.${PROOFCHECK_VERSION_MINOR}.${PROOFCHECK_VERSION_PATCH})

project(proofcheck VERSION ${PROOFCHECK_VERSION} LANGUAGES C CXX)

set(CMAKE_C_STANDARD 99)
set(CMAKE_CXX_STANDARD 17)

#Set the default build type if this is the first time cmake is run and nothing has been set
if (NOT EXISTS ${CMAKE_BINARY_DIR}/CMakeCache.txt)
    if (NOT CMAKE_BUILD_TYPE)
        set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Choose the type of build, options are: None Debug Release RelWithDebInfo MinSizeRel." FORCE)
    endif()
endif()

add_subdirectory(src)

set(INSTALL_HEADERS_DIR include/proofcheck)
include_directories(
        ${CMAKE_SOURCE_DIR}/src/api
        ${CMAKE_SOURCE_DIR}/src/drat-trim)


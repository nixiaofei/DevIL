cmake_minimum_required(VERSION 3.2)

set(
    CMAKE_TOOLCHAIN_FILE
    "${CMAKE_CURRENT_LIST_DIR}/cmake/toolchain.cmake"
    CACHE
    PATH
    "Default toolchain"
)

include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.20.26.tar.gz"
    SHA1 "04c42ba5194ca4e30d97f0e30adbb231facda048"
)

project(devil)

add_subdirectory(DevIL)

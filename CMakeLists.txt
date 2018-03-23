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
    URL "https://github.com/ruslo/hunter/archive/v0.20.27.tar.gz"
    SHA1 "aafefc6377dc9a25d84703702e22434cd6f71d5c"
)

project(devil)

add_subdirectory(DevIL)

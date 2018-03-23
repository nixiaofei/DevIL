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
    URL "https://github.com/ruslo/hunter/archive/v0.20.25.tar.gz"
    SHA1 "df89e927c0fbdf40f278114295d03bd2d7911ca2"
)

project(devil)

add_subdirectory(DevIL)

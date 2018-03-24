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
    URL "https://github.com/ruslo/hunter/archive/v0.20.28.tar.gz"
    SHA1 "8fee57e4232e35e28a88f0beafb5f2a739a3fa3c"
)

project(devil)

if("${CMAKE_SYSTEM_NAME}" STREQUAL "WindowsStore")
  add_definitions(-DDEVIL_WINDOWS_STORE)
endif()

add_subdirectory(DevIL)

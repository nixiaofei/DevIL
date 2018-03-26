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
    URL "https://github.com/ruslo/hunter/archive/v0.20.29.tar.gz"
    SHA1 "b1ee8476eb022eb651ad8c44a40d6718e2b6c4d8"
)

project(devil)

if("${CMAKE_SYSTEM_NAME}" STREQUAL "WindowsStore")
  add_definitions(-DDEVIL_WINDOWS_STORE)
endif()

add_subdirectory(DevIL)

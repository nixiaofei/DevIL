cmake_minimum_required(VERSION 2.6)

project(ImageLib)
# include our custom modules
list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake/Modules")

option(DEVIL_BUILD_ILUT "DevIL build ILUT" ON)

add_subdirectory(src-IL)
add_subdirectory(src-ILU)

if(DEVIL_BUILD_ILUT)
  add_subdirectory(src-ILUT)
endif()

option(IL_TESTS "build DevIL tests" ON)
if (IL_TESTS)
    ENABLE_TESTING()
    Add_Subdirectory(test)
endif()


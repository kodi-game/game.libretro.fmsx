cmake_minimum_required(VERSION 3.1)
project(game.libretro.fmsx)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(FMSX_LIB NAMES fmsx_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(FMSX_CUSTOM_BINARY ${FMSX_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} FMSX "")

include(CPack)

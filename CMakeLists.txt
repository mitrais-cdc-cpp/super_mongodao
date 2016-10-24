cmake_minimum_required(VERSION 3.1.0 FATAL_ERROR)
include(ExternalProject)

###############################################################################
## project BASE definition ####################################################
###############################################################################

set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_COLOR_MAKEFILE   ON)


set(poco_INSTALL_DIR "${CMAKE_SOURCE_DIR}/env")
set(poco_CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=${poco_INSTALL_DIR})
ExternalProject_Add(poco
  SOURCE_DIR ${CMAKE_SOURCE_DIR}/ojt_poco
  INSTALL_DIR ${poco_INSTALL_DIR}
  CMAKE_ARGS ${poco_CMAKE_ARGS}
)

#set(curl_INSTALL_DIR "${CMAKE_SOURCE_DIR}/env")
#set(curl_CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=${curl_INSTALL_DIR})
#ExternalProject_Add(curl
#  SOURCE_DIR ${CMAKE_SOURCE_DIR}/ojt_curl
#  INSTALL_DIR ${curl_INSTALL_DIR}
#  CMAKE_ARGS ${curl_CMAKE_ARGS}
#)

add_subdirectory(ojt_mongodao/)


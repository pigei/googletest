cmake_minimum_required(VERSION 2.6.2)

project( googletest-distribution )

enable_testing()

option(BUILD_GTEST "Builds the googletest subproject" OFF)

#Note that googlemock target already builds googletest
option(BUILD_GMOCK "Builds the googlemock subproject" ON)

#add postfix d for debug library versions (e.g. gtestd, gmockd)
SET(CMAKE_DEBUG_POSTFIX "d")

if(BUILD_GMOCK)
  add_subdirectory( googlemock )
elseif(BUILD_GTEST)
  add_subdirectory( googletest )
endif()

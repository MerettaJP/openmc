cmake_minimum_required(VERSION 3.16 FATAL_ERROR)
project(openmc_sources CXX)
add_library(source SHARED source_ring.cpp)
find_package(OpenMC REQUIRED)
if (OpenMC_FOUND)
  message(STATUS "Found OpenMC: ${OpenMC_DIR}")
endif()
target_link_libraries(source OpenMC::libopenmc)

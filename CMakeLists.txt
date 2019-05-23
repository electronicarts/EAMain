#-------------------------------------------------------------------------------------------
# Copyright (C) Electronic Arts Inc.  All rights reserved.
#-------------------------------------------------------------------------------------------
cmake_minimum_required(VERSION 3.1)
project(EAMain CXX)

#-------------------------------------------------------------------------------------------
# Library definition
#-------------------------------------------------------------------------------------------
file(GLOB EAMAIN_SOURCES "source/*.cpp" "source/internal/*.cpp")
add_library(EAMain ${EAMAIN_SOURCES})

#-------------------------------------------------------------------------------------------
# Defines
#-------------------------------------------------------------------------------------------
add_definitions(-D_CHAR16T)
add_definitions(-D_CRT_SECURE_NO_WARNINGS)
add_definitions(-DEAMAIN_NETWORK_CHANNEL_PORT=8080)

#-------------------------------------------------------------------------------------------
# Export Include Directories
#-------------------------------------------------------------------------------------------
target_include_directories(EAMain PUBLIC include)
target_include_directories(EAMain PUBLIC source)

#-------------------------------------------------------------------------------------------
# Package Dependencies 
#-------------------------------------------------------------------------------------------
target_link_libraries(EAMain EABase)
target_link_libraries(EAMain EAAssert)
target_link_libraries(EAMain EAStdC)


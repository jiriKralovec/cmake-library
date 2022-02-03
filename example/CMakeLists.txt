cmake_minimum_required(VERSION 3.20)

set(CMAKE_CXX_STANDARD 20)

#--------------------------------------------------------------------
# Get solution root
#--------------------------------------------------------------------
cmake_path(GET CMAKE_CURRENT_SOURCE_DIR PARENT_PATH CURRENT_SOURCE_DIR_PARENT)
cmake_path(APPEND CURRENT_SOURCE_DIR_PARENT "include")

#--------------------------------------------------------------------
# Set project name
#--------------------------------------------------------------------
project(MY_LIB_EXAMPLE)

#--------------------------------------------------------------------
# Add source
#--------------------------------------------------------------------
add_executable(MY_LIB_EXAMPLE main.cpp)

#--------------------------------------------------------------------
# Link libraries
#--------------------------------------------------------------------
target_link_libraries(MY_LIB_EXAMPLE MY_LIB)

#--------------------------------------------------------------------
# Link include directories
#--------------------------------------------------------------------
target_include_directories(MY_LIB_EXAMPLE PUBLIC ${CURRENT_SOURCE_DIR_PARENT})
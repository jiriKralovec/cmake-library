cmake_minimum_required(VERSION 3.20)

set(CMAKE_CXX_STANDARD 20)

#--------------------------------------------------------------------
# Get solution root
#--------------------------------------------------------------------
cmake_path(GET CMAKE_CURRENT_SOURCE_DIR PARENT_PATH LIB_PATH)
cmake_path(SET LIB_INCLUDE_PATH "${LIB_PATH}/include")

message(${LIB_PATH})
message(${LIB_INCLUDE_PATH})

#--------------------------------------------------------------------
# Set project name
#--------------------------------------------------------------------
project(MY_LIB_EXAMPLE)

#--------------------------------------------------------------------
# Add source
#--------------------------------------------------------------------
add_executable(MY_LIB_EXAMPLE main.cpp)
add_subdirectory(${LIB_PATH} library-build)

#--------------------------------------------------------------------
# Link libraries
#--------------------------------------------------------------------
target_link_libraries(MY_LIB_EXAMPLE MY_LIB)

#--------------------------------------------------------------------
# Link include directories
#--------------------------------------------------------------------
target_include_directories(MY_LIB_EXAMPLE PUBLIC ${LIB_INCLUDE_PATH})
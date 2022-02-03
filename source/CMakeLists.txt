add_library(MY_LIB MyLib/library.cpp ../include/MyLib/library.h)

target_include_directories(MY_LIB PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include/MyLib)
target_include_directories(MY_LIB PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/source/MyLib)
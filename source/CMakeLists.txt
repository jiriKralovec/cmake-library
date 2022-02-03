add_library(MY_LIB MyLib/library.cpp ../include/MyLib/library.h)

target_include_directories(MY_LIB PUBLIC ../include/MyLib)
target_include_directories(MY_LIB PRIVATE ../source/MyLib)
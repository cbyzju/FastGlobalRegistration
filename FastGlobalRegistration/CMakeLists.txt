cmake_minimum_required(VERSION 2.8)

#these are used under Linux system. In windows system, comment this line and select suitable visual studio compiler to compile this project
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")  
find_package(Eigen3 REQUIRED)
include_directories( EIGEN3_INCLUDE_DIR )
#you also include flann library to compile this project
include_directories(/usr/include/eigen3)
add_library(FastGlobalRegistrationLib STATIC app.cpp app.h)
add_executable(FastGlobalRegistration main.cpp)
TARGET_LINK_LIBRARIES(FastGlobalRegistration FastGlobalRegistrationLib)

cmake_minimum_required(VERSION 3.7)

add_definitions(-std=c++17)

set(CXX_FLAGS "-Wall")
set(CMAKE_CXX_FLAGS, "${CXX_FLAGS}")

project(HelloWorld)

set(Boost_USE_STATIC_LIBS ON) 
set(Boost_USE_MULTITHREADED ON)  
set(Boost_USE_STATIC_RUNTIME OFF) 

FIND_PACKAGE( Boost 1.80.0 COMPONENTS filesystem REQUIRED )
INCLUDE_DIRECTORIES( ${Boost_INCLUDE_DIR} )
include_directories(/usr/local/include)

add_executable(HelloWorld src/main.cpp)

TARGET_LINK_LIBRARIES(  HelloWorld 
                        LINK_PUBLIC ${Boost_LIBRARIES} )

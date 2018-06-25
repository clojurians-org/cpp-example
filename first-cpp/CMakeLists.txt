cmake_minimum_required (VERSION 2.6)
project (first)

add_executable(first Main.cpp)

set(Boost_USE_STATIC_LIBS        ON) # only find static libs
set(Boost_USE_MULTITHREADED      ON)
set(Boost_USE_STATIC_RUNTIME    OFF)
find_package(Boost REQUIRED system filesystem thread chrono coroutine context date_time program_options regex serialization)
include_directories(${Boost_INCLUDE_DIRS})
target_link_libraries (first ${Boost_LIBRARIES})

find_package (Threads REQUIRED)
target_link_libraries (first ${CMAKE_THREAD_LIBS_INIT})

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14")

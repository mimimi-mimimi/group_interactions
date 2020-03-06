cmake_minimum_required(VERSION 3.15)
project(group_interactions)

set(CMAKE_CXX_STANDARD 17)

set(SOURCES
        library.cpp)

set(HEADERS
        library.h)

add_library(${PROJECT_NAME} SHARED ${SOURCES} ${HEADERS})
cmake_minimum_required(VERSION 3.15)
project(group_interactions)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_AUTOMOC ON)

macro(FIND_QT5_MODULE module)
    find_package(Qt5${module})
    include_directories(${Qt5${module}_INCLUDE_DIRS})
endmacro(FIND_QT5_MODULE)

FIND_QT5_MODULE(Core)

message("Qt5Core_INCLUDE_DIRS=${Qt5Core_INCLUDE_DIRS}")
message("Qt5Core_DEFINITIONS=${Qt5Core_DEFINITIONS}")
message("Qt5Core_COMPILE_DEFINITIONS=${Qt5Core_COMPILE_DEFINITIONS}")

set(SOURCES
    library.cpp)

set(HEADERS
    library.h)

add_library(${PROJECT_NAME} SHARED ${SOURCES} ${HEADERS})

target_link_libraries(${PROJECT_NAME} Qt5::Core)
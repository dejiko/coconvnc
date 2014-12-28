project(coconvnc)
cmake_minimum_required(VERSION 2.8)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake/modules")

find_package(GTK2 2.6 REQUIRED gtk) 
find_package(LibVNCServer REQUIRED)

add_executable(coconvnc coconvnc.c)
target_link_libraries(coconvnc ${GTK2_LIBRARIES} ${LIBVNCCLIENT_LIBRARIES})
include_directories(${GTK2_INCLUDE_DIRS} ${LIBVNCCLIENT_INCLUDE_DIR})

install(TARGETS coconvnc RUNTIME DESTINATION bin)

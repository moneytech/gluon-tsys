cmake_minimum_required(VERSION 2.6)

project(libmeshutil C)

set_property(DIRECTORY PROPERTY COMPILE_DEFINITIONS _GNU_SOURCE)

add_library(meshutil SHARED libmeshutil.c)
set_property(TARGET meshutil PROPERTY COMPILE_FLAGS "-Wall -std=gnu99")
target_link_libraries(meshutil uci ubox ubus)
install(TARGETS meshutil
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib
)

install(FILES ${CMAKE_CURRENT_SOURCE_DIR}/libmeshutil.h DESTINATION include)

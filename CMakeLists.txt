cmake_minimum_required(VERSION 2.8)
project(ubj)

add_library(ubj ubjw.c ubjr.c ubjrw.c)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
add_subdirectory(tests)

set_target_properties(ubj PROPERTIES PUBLIC_HEADER "ubj.h")

add_subdirectory(tools)

install(TARGETS ubj
        EXPORT ubjTargets
	LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib
	PUBLIC_HEADER DESTINATION include
        )

cmake_minimum_required(VERSION 3.5)

project(
	cramfs-tools
	VERSION 2.1
	LANGUAGES C
)

find_package(ZLIB REQUIRED)

add_compile_options("-Wall")
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

add_executable(mkcramfs "mkcramfs.c")
add_executable(cramfsck "cramfsck.c")

target_link_libraries(mkcramfs PRIVATE ZLIB::ZLIB)
target_link_libraries(cramfsck PRIVATE ZLIB::ZLIB)

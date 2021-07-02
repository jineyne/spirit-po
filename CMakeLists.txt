cmake_minimum_required (VERSION 3.10)

# Find boost
find_package (BOOST REQUIRED)
find_path(BOOST_INCLUDE_DIR boost)
project (spirit-po)

add_library (spirit-po INTERFACE)
target_include_directories (spirit-po 
	INTERFACE 
		"$<BUILD_INTERFACE:${BOOST_INCLUDE_DIR}>"
		"$<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/include>")
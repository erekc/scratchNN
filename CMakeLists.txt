cmake_minimum_required(VERSION 3.5)

project(scratchNN LANGUAGES CXX)

set(CMAKE_INLCUDE_CURRENT_DIR ON)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(thirdparty/googletest)

file(GLOB SOURCES "src/*")
file(GLOB TEST "test/*")

add_executable(scratch-nn
	${SOURCES}
)

add_executable(utest
	${TEST}
)

target_link_libraries(utest gtest_main)

target_compile_options(scratch-nn PRIVATE -g -Wall -Wextra)

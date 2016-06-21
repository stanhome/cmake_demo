# @brief: main cmake.
# @author: stan
# @date: 2016-6-21

set(EXECUTABLE_OUTPUT_PATH ${hello_SOURCE_DIR}/bin)
set(SRC_LIST main.cpp)

include_directories(${hello_SOURCE_DIR}/include})
link_directories(${hello_SOURCE_DIR}/lib)

add_executable(hello ${SRC_LIST})
target_link_libraries(hello util)


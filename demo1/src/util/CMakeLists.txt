# @brief: build util static library.
# @author: stan
# @date: 2016-6-20

# define building output path.
set(LIBRARY_OUTPUT_PATH ${hello_SOURCE_DIR}/lib)
set(CMAKE_C_COMPILER g++)
set(SRC_LIST hello.c)

# define header file search path.
#       include_directories([AFTER|BEFORE] [SYSTEM] dir1 dir2 ...)
include_directories(${hello_SOURCE_DIR}/include)
# define library name, source file, static or dynamic.
#       add_library(libname [SHARED|STATIC|MODULE] [EXCLUDE_FROM_ALL] source1 source2 ... sourceN)
add_library(util STATIC ${SRC_LIST})


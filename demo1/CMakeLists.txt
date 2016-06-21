project(hello)

# [STATUS|WARNING|SEND_ERROR|FATAL_ERROR]
message("----------")
message(STATUS "[i]build 'hello' project begin...")

add_subdirectory(src)

install(FILES COPYRIGHT README DESTINATION share/doc/cmake_demo)
install(PROGRAMS run.sh DESTINATION bin)
install(PROGRAMS bin/hello DESTINATION bin)
install(DIRECTORY doc/ DESTINATION share/doc/cmake_demo)


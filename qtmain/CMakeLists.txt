cmake_minimum_required(VERSION 2.8.11)
project(QtMain)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

message(STATUS "==> building QT party <==")

# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
# Instruct CMake to run moc automatically when needed.
set(CMAKE_AUTOMOC ON)

# Find the QtWidgets library
find_package(Qt5Widgets REQUIRED)

set(SOURCE_FILES
        main.cpp
        mainwindow.cpp)

set(HEADER_FILES
        mainwindow.h)

set(qt_UI
        forms/mainwindow.ui)

set(qt_QRC
        forms/mainwindow.qrc)

qt5_wrap_ui(qt_UI_HEADERS ${qt_UI})
qt5_add_resources(qt_QRC_SOURCES ${qt_QRC})

message(STATUS "qt_UI_HEADERS:" ${qt_UI_HEADERS})

# Tell CMake to create the helloworld executable
add_executable(QtMain WIN32
        ${SOURCE_FILES}
        ${HEADER_FILES}
        ${qt_UI_HEADERS}
        ${qt_QRC_SOURCES})

# Use the Widgets module from Qt 5.
target_link_libraries(QtMain Qt5::Widgets)
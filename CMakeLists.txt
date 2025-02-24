cmake_minimum_required(VERSION 3.10)

project(wayland-log-reader)

include(GNUInstallDirs)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

find_package(Qt6 COMPONENTS Quick REQUIRED)

add_executable(wayland-log-reader
    main.cpp
    qml.qrc
)

target_link_libraries(wayland-log-reader
    Qt6::Quick
)

install(TARGETS wayland-log-reader DESTINATION ${CMAKE_INSTALL_BINDIR})

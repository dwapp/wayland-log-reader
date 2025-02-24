cmake_minimum_required(VERSION 3.16)

project(wayland-log-reader VERSION 0.1 LANGUAGES CXX)

include(GNUInstallDirs)

find_package(Qt6 COMPONENTS Quick REQUIRED)

qt_standard_project_setup(REQUIRES 6.5)

qt_add_executable(wayland-log-reader
    Main.cpp
)

qt_add_qml_module(wayland-log-reader
    URI wlog-reader
    VERSION 1.0
    QML_FILES
        Main.qml
        ObjectLabel.qml
        ArgumentItem.qml
        wayland-debug-tools.js
        lodash.js
)

target_link_libraries(wayland-log-reader
    PRIVATE Qt6::Quick
)

install(TARGETS wayland-log-reader DESTINATION ${CMAKE_INSTALL_BINDIR})

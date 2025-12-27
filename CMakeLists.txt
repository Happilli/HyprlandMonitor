cmake_minimum_required(VERSION 3.20)
project(HyprlandMonitor)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_AUTOMOC ON)

find_package(Qt6 REQUIRED COMPONENTS Core Qml Network)

qt_add_qml_module(hyprlandmonitor
    URI HyprlandMonitor
    VERSION 1.0
    OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/HyprlandMonitor
    SOURCES
        hyprlandmonitor.cpp
        hyprlandmonitor.hpp
)

target_link_libraries(hyprlandmonitor PRIVATE
    Qt6::Core
    Qt6::Qml
    Qt6::Network
)

set_target_properties(hyprlandmonitorplugin PROPERTIES
    INSTALL_RPATH "$ORIGIN"
    BUILD_WITH_INSTALL_RPATH TRUE
)

install(TARGETS hyprlandmonitor hyprlandmonitorplugin
    LIBRARY DESTINATION ${CMAKE_INSTALL_PREFIX}
)

install(FILES ${CMAKE_BINARY_DIR}/HyprlandMonitor/qmldir
    DESTINATION ${CMAKE_INSTALL_PREFIX}
)

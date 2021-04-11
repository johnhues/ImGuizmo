cmake_minimum_required(VERSION 3.11 FATAL_ERROR)
project(imguizmo LANGUAGES CXX)

# C++ settings
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
add_definitions(-D_UNICODE -DUNICODE)

add_library(imguizmo ImGuizmo.cpp)
target_include_directories(imguizmo PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(imguizmo imgui)

cmake_minimum_required(VERSION 3.11 FATAL_ERROR)
project(imguizmo LANGUAGES CXX)
include(FetchContent)

# C++ settings
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
add_definitions(-D_UNICODE -DUNICODE)

FetchContent_Declare(imgui
	GIT_REPOSITORY https://github.com/johnhues/imgui.git
	GIT_TAG 640bc056a97829bb38562954a9895f490a72a1bc
)
FetchContent_GetProperties(imgui)
if(NOT imgui_POPULATED)
	FetchContent_Populate(imgui)
	add_subdirectory(${imgui_SOURCE_DIR} ${imgui_BINARY_DIR})
endif()

add_library(imguizmo ImGuizmo.cpp)
include_directories(${imgui_SOURCE_DIR})
target_link_libraries(imguizmo imgui)

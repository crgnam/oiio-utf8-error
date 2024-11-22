cmake_minimum_required(VERSION 3.19)

project(Example LANGUAGES CXX VERSION 0.8.0)
set(CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

find_package(OpenImageIO CONFIG REQUIRED)

add_executable(example example.cpp)
target_link_libraries(example PRIVATE OpenImageIO::OpenImageIO)
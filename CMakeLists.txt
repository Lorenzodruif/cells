cmake_minimum_required(VERSION 3.20)
project(cells LANGUAGES C)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)

# Grab all .c files from src
file(GLOB SRC_FILES src/*.c)

add_executable(cells ${SRC_FILES})

# Include raylib headers
target_include_directories(cells PRIVATE include)

target_include_directories(cells PRIVATE ${PROJECT_SOURCE_DIR}/include)
target_link_directories(cells PRIVATE ${PROJECT_SOURCE_DIR}/lib)
target_link_libraries(cells PRIVATE raylib opengl32 gdi32 winmm)
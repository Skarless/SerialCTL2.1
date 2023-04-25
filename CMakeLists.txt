cmake_minimum_required(VERSION 3.5)
project(serialctl C)

set(CMAKE_C_STANDARD 11)

find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})

set(SOURCES base64.c crc16.c serio.c main.c joystick.c)
add_executable(serialctl ${SOURCES})

target_compile_options(serialctl PRIVATE -Wall -Werror -g ${SDL_CFLAGS} ${CFLAGS})
target_link_libraries(serialctl ${SDL2_LIBRARIES})
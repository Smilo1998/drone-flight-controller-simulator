# Minimum CMake version required
cmake_minimum_required(VERSION 3.10)

# Project name and version
project(DroneFlightController VERSION 1.0 LANGUAGES C)

# Specify C standard (C99 for modern C features)
set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED True)

# Add source files
set(SOURCES
    src/main.c
    src/sensor.c
    src/controller.c
    src/output.c
)

# Add header files for proper include
set(HEADERS
    src/sensor.h
    src/controller.h
    src/output.h
)

# Add executable
add_executable(DroneFlightController ${SOURCES} ${HEADERS})

# Include directories
target_include_directories(DroneFlightController PRIVATE ${CMAKE_SOURCE_DIR}/src)

# Enable compiler warnings (optional, for better debugging)
target_compile_options(DroneFlightController PRIVATE -Wall -Wextra -pedantic)

# Optionally enable debugging symbols (useful during development)
set(CMAKE_BUILD_TYPE Debug)

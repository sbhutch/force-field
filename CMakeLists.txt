cmake_minimum_required(VERSION 3.20)
project(force-field)

find_package(SDL3 CONFIG REQUIRED)

file(
    GLOB_RECURSE
    PROJECT_HEADER_FILES src/*.h
    PROJECT_SOURCE_FILES src/*.c
)

add_executable(
    force-field
    ${PROJECT_HEADER_FILES}
    ${PROJECT_SOURCE_FILES}
)

target_link_libraries(
    force-field
    PRIVATE
    SDL3::SDL3
)

target_compile_features(
    force-field
    PRIVATE
    c_std_99
)

target_compile_options(
    force-field
    PRIVATE
    -Wall
    -Wconversion
    -Werror
    -Wextra
    -Wpedantic
)

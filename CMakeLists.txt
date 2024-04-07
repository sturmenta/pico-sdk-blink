# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

# initialize pico-sdk from GIT
# (note this can come from environment, CMake cache etc)
set(PICO_SDK_FETCH_FROM_GIT on)

# pico_sdk_import.cmake is a single file copied from this SDK
# note: this must happen before project()
include(pico_sdk_import.cmake)

project(my_project)

# initialize the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(blink blink.cpp )

pico_set_program_name(blink "Blink")
pico_set_program_version(blink "0.1")

pico_enable_stdio_uart(blink 1)
pico_enable_stdio_usb(blink 0)

# Add the standard library to the build
target_link_libraries(blink pico_stdlib)

# Add any user requested libraries
target_link_libraries(blink
        hardware_clocks
        )

pico_add_extra_outputs(blink)


# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialise pico_sdk from installed location
# (note this can come from environment, CMake cache etc)
set(PICO_SDK_PATH "C:/Program Files/Raspberry Pi/Pico SDK v1.5.0/pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(mpu6050_i2c C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(mpu6050_i2c mpu6050_i2c.c)

pico_set_program_name(mpu6050_i2c "mpu6050_i2c")
pico_set_program_version(mpu6050_i2c "0.1")

pico_enable_stdio_uart(mpu6050_i2c 0)
pico_enable_stdio_usb(mpu6050_i2c 1)

# Add the standard library to the build
target_link_libraries(mpu6050_i2c pico_stdlib hardware_i2c)

pico_add_extra_outputs(mpu6050_i2c)

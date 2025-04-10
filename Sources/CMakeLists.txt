cmake_minimum_required(VERSION 3.10.0)
project(SampleProject VERSION 0.1.0 LANGUAGES C CXX)

set (OUTPUT_DIR ${CMAKE_CURRENT_SOURCE_DIR}../Releases)

add_executable(SampleProject main.cpp)

add_custom_command(TARGET SampleProject POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy
            $<TARGET_FILE:SampleProject>
            ${CMAKE_CURRENT_SOURCE_DIR}/Releases/SampleProject
)
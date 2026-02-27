cmake_minimum_required(VERSION 3.18)
project(UCLauncher)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(uc.launcher WIN32
    uc.launcher.cpp
    uc.launcher.rc
)

if(WIN64)
    target_compile_definitions(uc.launcher PRIVATE -DPLATFORM_WINDOWS64)
endif()

set_target_properties(uc.launcher PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
    WIN32_EXECUTABLE TRUE
    LINK_FLAGS "/SUBSYSTEM:WINDOWS"
)

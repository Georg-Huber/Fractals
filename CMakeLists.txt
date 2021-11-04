cmake_minimum_required(VERSION 3.20)
project(Fractals)

set(CMAKE_CXX_STANDARD 17)

add_subdirectory(external/wxWidgets)

add_executable(${PROJECT_NAME} src/main.cpp)

target_include_directories(${PROJECT_NAME}
        PUBLIC
        $<INSTALL_INTERFACE:include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
        wxWidgets
        )

target_link_libraries(${PROJECT_NAME}
        PUBLIC
        wx::net
        wx::core
        wx::base
        )



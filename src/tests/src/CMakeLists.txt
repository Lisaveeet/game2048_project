cmake_minimum_required(VERSION 3.5)

project(src LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(SFML_DIR "../libs/SFML-2.5.1/lib/cmake/SFML")

find_package(SFML 2.5 COMPONENTS graphics audio system REQUIRED)

add_executable(src main.cpp
        Field/fieldcontroller.h Field/fieldcontroller.cpp
        Field/fieldmodel.cpp Field/fieldmodel.h
        Field/fieldview.h Field/fieldview.cpp
        constants.h utils.h
        game.h game.cpp)

target_link_libraries(src PRIVATE sfml-graphics sfml-audio)

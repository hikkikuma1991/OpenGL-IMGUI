cmake_minimum_required(VERSION 2.8)
project(OpenGl CXX)

set(CMAKE_CXX_COMPILER "clang++")
set(CMAKE_CXX_FLAGS "-std=c++1z")



include_directories(./libs/imgui)
include_directories(./libs/gl3w)
aux_source_directory(./src SRC_LIST)
add_executable(opengl ${SRC_LIST} ./libs/imgui/imgui.o ./libs/imgui/imgui_draw.o ./libs/gl3w/GL/gl3w.o)

target_link_libraries(opengl -lstdc++)
target_link_libraries(opengl -lglfw3)
target_link_libraries(opengl -lsoil)
target_link_libraries(opengl -lglew)
target_link_libraries(opengl -lassimp)
target_link_libraries(opengl "-framework OpenGl")
target_link_libraries(opengl "-framework Cocoa")
target_link_libraries(opengl "-framework IOKit")
target_link_libraries(opengl "-framework Corevideo")
target_link_libraries(opengl "-framework Carbon")

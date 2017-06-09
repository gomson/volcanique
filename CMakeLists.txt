cmake_minimum_required(VERSION 3.0.2)
project(volcanique)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

add_executable(vktest main.cpp)

target_link_libraries(vktest PUBLIC "${CONAN_LIBS}")
set_target_properties(vktest PROPERTIES LINK_FLAGS "${CONAN_EXE_LINKER_FLAGS}")

cmake_minimum_required(VERSION 3.0.2)
project(volcanique)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

find_package(Vulkan REQUIRED)

add_executable(vktest main.cpp)

include_directories("${Vulkan_INCLUDE_DIR}")
target_link_libraries(vktest PUBLIC "${CONAN_LIBS}" "${Vulkan_LIBRARY}")
set_target_properties(vktest PROPERTIES LINK_FLAGS "${CONAN_EXE_LINKER_FLAGS}")

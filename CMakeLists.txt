cmake_minimum_required(3.0.2)
project(volcanique)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

add_executable(test main.cpp)

target_link_libraries(test PUBLIC "${CONAN_LIBS}")
set_target_properties(test PROPERTIES LINK_FLAGS "${CONAN_EXE_LINKER_FLAGS}")

Volcanique
----------

Code written while following the [Vulkan Tutorial](https://vulkan-tutorial.com/), using the [conan](https://github.com/conan-io/conan) package manager for quick dependency deployment from [bintray](https://bintray.com/conan).

Prerequisites:

- A compiler. The code may work on Linux, but I am only using Windows with Visual Studio for now.
- [LunarG SDK](https://www.lunarg.com/vulkan-sdk/)
- [conan](https://github.com/conan-io/conan)
- [CMake](https://cmake.org/)
- [Git](https://git-scm.com/)

GLM and GLFW, which are referenced by the code, are deployed by conan. In order for GLFW to "see" the Vulkan SDK, make sure you compile it locally. Here's how to build and run the project:

	git clone https://github.com/dimi309/volcanique
	cd volcanique
	mkdir build
	cd build
	conan install .. --build glfw
	cmake ..
	cmake --build .
	cd bin
	vktest.exe

Depending on your Visual Studio version, you can get some compiler detection and linking errors. Feel free to [ask me](https://github.com/dimi309/volcanique/issues) and I'll be happy to help.

Nonetheless, here's a sure-fire way to make the above mentioned commands work just like that with Visual Studio 2017:

Set the vs150comntools environment variable:
	
	set vs150comntools=C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\Tools\

In your home directory, make sure that the .conan/conan.conf file contains these lines exactly under settings_defaults:

	[settings_defaults]

	arch=x86
	build_type=Debug
	os=Windows
	compiler=Visual Studio
	compiler.version=15
	compiler.runtime=MDd

# CMakeLists

## Introduction
CMake allows the description of the project by listing instructions and directives in input source files named `CMakeLists.txt`. Mbed OS has many of these files which are included in the build from a top-level `CMakeLists.txt` at the root of the project.
We will briefly cover how `CMakeLists.txt` are used within the Mbed OS repository.

## CMake target selection

Mbed OS is built as a collection of all interdependent libraries essential to run the most basic application. This collection of library is used to create the CMake library target aptly named `mbed-core`. `mbed-core` is the foundation library which is linked with other libraries to make more complex systems. Applications that require an RTOS should link with the `mbed-os` CMake library target which includes `mbed-core` as well as the library that implements the RTOS. Applications destined to run on hardware with greater memory constrains and do not require an RTOS should use the `mbed-baremetal` CMake library instead of `mbed-os`.

Other libraries are optional and can be linked with the application CMake target as required. To identify the name of the optional library to link with, inspect the CMake input source file (`CMakeLists.txt`) in the directory containing the source files of the library required. For example if LoRaWAN is required, inspect `connectivity/lorawan/CMakeLists.txt` and you see that the CMake library which implements it is `mbed-lorawan`.
All Mbed CMake libraries are prefixed with `mbed-`.

The CMake targets defined in the `CMakeLists.txt` of a subdirectory must be explicitly built as they are excluded from the `ALL` of the parent directory. This is because we add subdirectories using `EXCLUDE_FROM_ALL` so only the features and BSP relevant to a project and Mbed boards are excluded in the build unless needed.

## Library configuration
Source files are included in libraries by listing them in `CMakeLists.txt` files using `target_sources()`. Some source code are provided in Mbed as pre-built libraries and are added to libraries using `target_link_libraries()`. `target_link_libraries()` is also used to link other Mbed libraries if there are dependencies.
Header files are included by listing the directories where they are found using `target_include_directories()`. Additionally, compile defintions are added to libraries using `target_compile_definitions()`.

## Board support
All Mbed boards can be built with CMake. An Mbed board specific configuration CMake module is generated by Mbed CLI 2 to help in the selection of the board support package. See Mbed CLI 2 for more information about the generated CMake module.
Post build operations required for some Mbed boards are triggered in CMake by invoking the appropriate script.
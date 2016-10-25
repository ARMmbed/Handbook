## mbed OS Software Design Guide ##

```
Principles of mbed Software
- Consistent 
- Intuitive 
- Simple 
- Reliable 
```

### Style ###
1. Please refer to the mbed style guide:
   https://docs.mbed.com/docs/mbed-os-handbook/en/5.2/cont/code_style/

### Organization ###
The mbed OS codebase is organized into conceptual submodules to limit the scope/complexity of individual contributions. These modules are contained in the mbed OS codebase as a single git repo. The following model is also suggested for external libraries. 
 
1. Modules should be logically grouped in the OS tree. Avoid generic words, be intentional with naming.
```
 - mbed-os
    |- rtos - user API + any layer required to fit into mbed OS
    |   |- rtx - third-party implementation
    |   |- windows - third-party implementation
    |   `- tests
    |       |- unit - rtos related unit tests
    |       `- functional - rtos related functional tests
    |- drivers - user API on-chip hardware interfaces (Ticker, DigitalOut, etc)
    |- util - chip-independent layer (retarget, toolchain, etc)
    |   `- bootloader - chip-independent bootloader
    |- net - networking API
    |   |- stack - network implementations
    |   |   |-lwip
    |   |   `- nanostack
    |   `- tests - network tests
    `- tests
        |- integration - mbed OS integration tests
        `- smoke - mbed OS smoke tests (blinky, etc)
```
1. Each source file should be prefixed with the module name followed by an underscore.
  1. This is to avoid conflicts with other similarly named files in different modules such as `nanostack/thread.c` and `drivers/Thread.cpp`. Not all toolchains are able to support object files with the same name.
```
mbed-os/rtos/rtos_thread.cpp
mbed-os/rtos/rtos_semaphore.cpp
mbed-os/drivers/drivers_analog_in.cpp
```
1. Header files should always be included using the module directory in the path.
  1. examples: `#include “lwip/lwip-interface.h”`, `#include “drivers/Ticker.h”`
  1. Limit the include path to only the module directory, this allows the module to be moved in the future.
1. A single header file is suggested as an entry point for the module from user space.
  1. examples: `mbed.h`, `rtos.h`
1. Header files should limit external includes to avoid indirectly exposing unrelated APIs. Header files should not expand namespaces.
1. In C++ modules, the API should be contained in a namespace that matches the module’s name.
  1. examples: `mbed::Ticker`, `rtos::Thread`, `netsocket::Socket`
1. In C modules, every non-static function and type should be prefixed with the module’s name followed by an underscore
  1. examples: `mbed_critical_section_enter()`, `lwip_gethostbyname(host)`
1. A module contained in the mbed OS codebase may be mirrored in a separate repo. If this is the case, the repo should be clearly identified and linked to from the module's readme.
1. Special directories should follow consistent naming convention
 
### Contribution ###
1. Please refer to the mbed contribution guide:
   https://docs.mbed.com/docs/mbed-os-handbook/en/5.2/cont/contributing/
1. Each pull-request should serve a single purpose
1. The code must compile every commit
1. Commit message should be prefixed with the submodule name and a colon.
```
lwip: Fixed buffer overrun in rx loop 

The rx loop did not properly wait for rx semaphore to release
causing the buffer to overrun
```
1. Patches must land on master before being backported to one or many release branches.
1. Feature development may happen a separate branch and is brought to master when complete.
1. The master branch and release branches must never be rewritten.
1. All contributers must sign the CLA:  
  https://developer.mbed.org/contributor_agreement
1. Only acceptable licenses will be accepted for incoming source.
  1. Currently acceptable licenses:
    1. MIT
    1. Apache
    1. Permissive Binary License

### API Design ###
A general module can be split into two APIs, the frontend (or user API) and the backend (or porting layer). The user API describes the programmer interface that the library implements. For mbed OS, the user-facing API should adopt a C++ class-based interface, while the porting layer should adopt a C-compatible interface.

### API Design - User API ###
1. Each module should provide an object-oriented C++ user API
1. Current standard is strictly C++03 for portability
1. State should be contained in relevant C++ classes
1. Be hesitant to adopt language features nonexistant in the codebase.
  1. Think C with the good parts of C++
  1. Don't make users learn new things
  1. Exceptions and RTTI is disabled
  1. Avoid the STL due to unknown impact on system resources
1. Prefer C language features over C++ language features
  1. Use different function names over ambiguous overloads
  1. Do use `uint8_t read_8(void)`, `uint16_t read_16(void)`, `uint32_t read_32(void)`
  1. Do use `void write_8(uint8_t)`,  `void write_16(uint16_t)`, `void write_32(uint32_t)`
  1. Limit templates to types and array-sizes
1. Use pointers and references based on the following rules. Use appropriate documentation where ownership may be ambiguous
  1. Use a copy or immutable reference to pass types with value semantics
  1. Use a pointer to borrow ownership of dynamic polymorphic classes
  1. Use a pointer to transfer ownership of dynamic polymorphic classes. Ownership must be clearly document if the ownership is transfered
  1. Pointers should be used over references
    1.More familiar to C users
    1. Ownership is syntactically clear
1. Organize classes into two types
  1. Types with value semantics such as SocketAddress and Callback
    1. User-friendly alternatives to builtin-types
    1. Can not be extended (suffer from object slicing)
    1. Pass by value, no memory management needed (handled on stack)
    1. If possible pass by const-reference is suggested to reduce copying
    1. Must be cheap to copy
    1. Should be small (<= 16 bytes), this does not include indirectly referenced memory
  1. Dynamic polymorphic classes such as Ticker and EthernetInterface
    1. Participate in class hierarchy
    1. Can be abstracted by interfaces
    1. Extendable - should have virtual table
      1. Must contain virtual destructor if overloadable
    1. Passed by pointer, memory management should be left up to user
    1. Should declare copy constructor and copy assignment operator as private
      1. If copying is really needed, a virtual `clone` member function is suggested to avoid issues with slicing and indicate that the clone is a non-trivial operation
    1. If a class contains a very large memory region (> 64 bytes), dynamically allocating the region is preferred
      1. Avoids stack overflows if the user instantiates the class on the stack
1. A class should have one responsibility
  1. examples: `UDPSocket` vs `TCPSocket`, `Ticker` vs `Timer`
1. Inheritance should be used where there is a “is a” relationship.
  1. examples: `UDPSocket` and `Socket`
  1. Abstract base classes are preferred over template-based polymorphism to avoid code size increase.
  1. Composing abstract interfaces is preferred in C++ code over preprocessor-based conditional compilation and other forms of indirect dispatch
1. Do not declare objects in global scope (applications should allocate global objects). Objects declared in global scope rarely get garbage-collected by compilers during link time. This can cause significant bloat in the size of an application.
1. Use get/set functions with private member variables to hide internal state from the user.
1. Avoid operations that can fail if you can't signal an error
  1. Class constructors should not fail
1. Non-recoverable errors (ie OOM and mutex lock in interrupt) should not return to users
1. Recoverable errors (ie UDP packet loss) should be propagated to the user via error code

### API Design - Porting Layer ###
1. Each module should provide a C compatible porting layer
1. Current standards are strictly C99 for portability
1. Porting layer should make no assumptions about how it is consumed
1. State should be contained in a struct passed by pointer from the user API
  1. Global state should be avoided
1. The porting layer should be designed to allow as much variance in the implementation as is reasonable
1. Simplicity is beautiful

### Thread and IRQ safety ###
Full documentation:
https://docs.mbed.com/docs/mbed-os-handbook/en/5.2/concepts/thread_safety/

1. User APIs should be thread safe
1. If a user API is intended to be interrupt safe, this should be clearly documented
1. If a user API is unable to be thread safe, this should be clearly documented with warning notation
  1. consistent across all APIs - warning not thread safe
1. A module’s porting layer should be designed for non-thread-safe implementations
1. If a callback is called in interrupt context, the API responsible should be clearly documented with warning notation
  1. consistent across all APIs - warning called from interrupt context

### Documentation ###
1. Each function and class in a module should provide a doxygen comment that documents the function and each argument and return value.
``` cpp
/** Wait until a Mutex becomes available.
 *
 * @param   millisec  timeout value or 0 in case of no time-out. (default: osWaitForever)
 * @return  status code that indicates the execution status of the function.
 */
osStatus lock(uint32_t millisec=osWaitForever);
```
1. Each class should contain a simple example usage in the class's doxygen in the class's header file 
1. Each module should provide a README that documents the module
  1. The README should start with a small paragraph describing the module to users with no prior information
  1. The README should contain a code example showing how to use the module
  1. If a module contains a porting layer, instructions on how to port should be provided in the module’s README
  1. If a module contains tests, instruction on how to test should be provided in the module’s README
1. Extended documentation should be located in the module’s `docs` directory with appropriate links from the module’s README.

### Testing ###
Full documentation:
https://docs.mbed.com/docs/mbed-os-handbook/en/5.2/advanced/testing/

1. Each modules should contain a `tests` directory with tests that cover the module’s functionality
1. Tests should be organized based on the class being tested
  1. Roughly one test file per class
1. Tests included in the codebase must be compatible with the mbed OS test framework
1. Every bug fix should include an additional test case identifies the bug and deterministically fails before the bug is fixed to avoid regressions.
 
### Configuration ###
mbed OS provides a powerful configuration system for application development. However, modules should also be concerned with remaining configurable outside of the mbed build system. Modules should provide well documented configuration options in a simple header file.

Full documentation:
https://docs.mbed.com/docs/mbed-os-handbook/en/5.2/advanced/config_system/
 
1. Each module should provide a `module_lib.json` or similar with configuration options
1. Each config option should contain documentation over the purpose of the config option and the impact the config option has on the system.
1. Each config option should provide a reasonable default in the case the config option is not defined to help porting to new targets.
1. Config options should not change the behaviour of the API.
  1. Multiple classes are preferred where different functionality is needed in the user API
1. Configuration should be overrideable from the targets and the application
1. The default choice of optimization should be size on all platforms

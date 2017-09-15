#### PortIn

Use the PortIn interface to read an underlying GPIO port as one value. This is much faster than [BusIn](/docs/v5.4/reference/api-references.html#busin) because you can read a port in one go, but it is much less flexible because you are constrained by the port and bit layout of the underlying GPIO ports.

A mask can be supplied so only certain bits of a port are used, allowing other bits to be used for other interfaces.

##### PortIn class reference

[![View code](https://www.mbed.com/embed/?type=library)](/docs/v5.4/mbed-os-api-doxy/classmbed_1_1_port_in.html)

##### PortIn Hello World!

[![View code](https://www.mbed.com/embed/?url=https://developer.mbed.org/users/mbed_official/code/PortIn_HelloWorld/)](https://developer.mbed.org/users/mbed_official/code/PortIn_HelloWorld/file/92064442fd12/main.cpp)

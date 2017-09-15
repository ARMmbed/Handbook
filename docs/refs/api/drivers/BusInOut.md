#### BusInOut

Use the BusInOut interface as a bidirectional bus that supports up to 16 [DigitalInOut](/docs/v5.4/reference/api-references.html#digitalinout) pins that you can read and write as one value.

You can use any of the numbered Arm Mbed pins as a DigitalInOut.

<span class="notes">**Note:** The order of pins in the constructor is the reverse order of the pins in the byte order. If you have `BusOut(a,b,c,d,e,f,g,h)`, then the order of bits in the byte is `hgfedcba` with `a` being bit 0, `b` being bit 1, `c` being bit 2 and so on.</span>

##### BusInOut class reference

[![View code](https://www.mbed.com/embed/?type=library)](/docs/v5.4/mbed-os-api-doxy/classmbed_1_1_bus_in_out.html)

##### BusInOut Hello World!

[![View code](https://www.mbed.com/embed/?url=https://developer.mbed.org/teams/mbed_example/code/BusInOut_HelloWorld/)](https://developer.mbed.org/teams/mbed_example/code/BusInOut_HelloWorld/file/68629c6c4970/main.cpp)

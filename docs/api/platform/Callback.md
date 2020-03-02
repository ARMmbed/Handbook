# Callback

A callback is a user provided function that a user may pass to an API. The callback allows the API to execute the user’s code in its own context.

This is the technical reference for callbacks. You should read the [Callbacks](platform.html#callbacks) section of the [Platform Overview](platform.html) first for deeper insight into their use.

## Calling callbacks

Callbacks overload the function call operator, so you can call a Callback like you would a normal function:

```c++
void run_timer_event(Callback<void(float)> on_timer) {
    on_timer(1.0f);
}
```

The only thing to watch out for is that the Callback type has an empty Callback, just like a null function pointer. Default initialized callbacks are empty and assert if you call them. If a callback may be empty, you need to check if it is empty before calling it.

``` c++
void run_timer_event(Callback<void(float)> on_timer) {
    if (on_timer) {
        on_timer(1.0f);
    }
}
```

You can reset Callbacks to empty by assigning `nullptr`.

The Callback class is what’s known in C++ as a “Concrete Type”. That is, the Callback class is lightweight enough to be passed around like an int, pointer or other primitive type.

## Callback class reference

[![View code](https://www.mbed.com/embed/?type=library)](https://os.mbed.com/docs/mbed-os/6.0.0-preview/mbed-os-api-doxy/classmbed_1_1_callback.html)

## Serial passthrough example with callbacks
[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed_example/code/rtos_threading_with_callback/)](https://os.mbed.com/users/mbedAustin/code/SerialPassthrough/file/96cb82af9996/main.cpp)

## Thread example with callbacks

The Callback API provides a convenient way to pass arguments to spawned threads. This example uses a C function pointer in the Callback.

 [![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed_example/code/rtos_threading_with_callback/)](https://os.mbed.com/teams/mbed_example/code/rtos_threading_with_callback/file/5938bdb7b0bb/main.cpp)

## Sonar example

Here is an example that uses everything discussed in the [introduction to callbacks](platform.html#callbacks) document in the form of a minimal Sonar class. This example uses a C++ class and method in the Callback.

[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed_example/code/callback-sonar-example/)](https://os.mbed.com/teams/mbed_example/code/callback-sonar-example/file/1713cdc51510/main.cpp)

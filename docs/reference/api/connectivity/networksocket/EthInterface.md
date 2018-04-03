## Ethernet

The `EthInterface` provides a C++ API for connecting to the internet over Ethernet. By default, this class does not require any configuration. It is able to pick up the default Ethernet driver for the target and select the correct network stack.

### Usage

To statically initialize the driver, create an object without passing any parameters:

```cpp
EthernetInterface eth;
```

Then, if the default configuration is enough, bring up the interface:

```cpp
nsapi_error_t status = eth.connect();
```

Now, the interface is ready to be used for [network sockets](/docs/development/reference/network-socket.html).

```cpp
// Open a TCP socket
TCPSocket socket;
socket.open(&eth);

// Open a UDP socket
UDPSocket socket;
socket.open(&eth);
```

### Configuration

For EthernetInterface, there are two possible configurations:

- Use DHCP for network addressing. This is the default.
- Use statically configured IP addresses.

Refer to the API below for how to set the IP addresses by calling the `set_network()` function.

### EthInterface class reference

[![View code](https://www.mbed.com/embed/?type=library)](http://os-doc-builder.test.mbed.com/docs/development/mbed-os-api-doxy/class_eth_interface.html)

### EthInterface examples

Here is an example of an HTTP client program. The program brings up Ethernet as the underlying network interface and uses it to perform an HTTP transaction over a TCPSocket:

[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed_example/code/TCPSocket_Example/)](https://os.mbed.com/teams/mbed_example/code/TCPSocket_Example/file/6b383744246e/main.cpp)

Here is an example showing how to register a status callback that gets triggered when connection state changes. This also works with other network interfaces if support is provided.

[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed_example/code/TCPSocket_ConnStateCb_Example/)](https://os.mbed.com/teams/mbed_example/code/TCPSocket_ConnStateCb_Example/file/8a8191e3d305/main.cpp)

### Related content

- [Network socket](/docs/development/reference/network-socket.html) API reference overview.

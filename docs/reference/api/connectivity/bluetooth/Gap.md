## GAP

The Generic Access Profile is the layer of the stack that handles connectivity tasks. This includes link establishment and termination, advertising and scanning.

Devices with data to publish can use GAP to advertise. They can include the data in the advertisement itself or inside the scan response or leave a peer device to query it after the connection has been established.

The other side of the process is the act of scanning, which listens for advertisements, allows you to query the advertisers for more data through a scan request or to connect in order to query the peer device for the data we want.

Advertising, scanning and connection all have parameters that let you find a compromise between desired power consumption levels and latency and efficiency of these processes.

### GAP class reference

[![View code](https://www.mbed.com/embed/?type=library)](https://os.mbed.com/docs/v5.6/mbed-os-api-doxy/class_gap.html)

### GAP example

Here is an example demonstrating how to use the GAP API to advertise, scan, connect and disconnect and how parameters influence efficiency of these actions.

[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-ble-GAP/)](https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-ble-GAP)

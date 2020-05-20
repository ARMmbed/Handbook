<h1 id="mesh-api">Mesh</h1>

<span class="images">![](https://os.mbed.com/docs/mbed-os/development/mbed-os-api-doxy/class_mesh_interface.png)<span>MeshInterface class hierarchy</span></span>

The Arm Mbed Mesh API allows the application to use the IPv6 mesh network topologies through the [Nanostack](../apis/6LoWPAN-ND-tech.html) networking stack.

Mbed OS provides three types of IPv6-based mesh networks:

- [Wi-SUN](../apis/wisun-tech.html), following the specification from the Wi-SUN alliance.
- [Thread](../apis/connectivity.html), following the specification from Thread Group.
- [6LoWPAN-ND](../apis/6LoWPAN-ND-tech.html), loosely following the Zigbee-IP specification.

The application can use the `LoWPANNDInterface`, `WisunInterface` or `ThreadInterface` object to connect to the mesh network. When successfully connected, the application can use the Mbed [C++ socket APIs](network-socket.html) to create a socket to start communication with a remote peer. You can use the [Network status API](network-status.html) to monitor changes in the network status.

You can configure the mesh interface by providing values in `mbed_app.json`, as the [mesh configuration](../apis/configuration-mesh.html) section documents.

## Mesh class reference

[![View code](https://www.mbed.com/embed/?type=library)](https://os.mbed.com/docs/mbed-os/development/mbed-os-api-doxy/class_mesh_interface.html)

## Mesh example

The following code snippet illustrates how you can use the MeshInterface API:

[![View code](https://www.mbed.com/embed/?url=https://github.com/ARMmbed/mbed-os-snippet-Mesh_Ex1)](https://github.com/ARMmbed/mbed-os-snippet-Mesh_Ex1/blob/master/main.cpp)


## Related content

- [Mesh tutorial](../apis/connectivity-tutorials.html) to start using mesh technology.
- [Light control tutorial](../apis/light-control.html), in which devices can control the LED status of all devices in the network.
- [Mesh configuration](../apis/configuration-mesh.html).
- [Networking connectivity](../apis/connectivity.html) architecture reference material.

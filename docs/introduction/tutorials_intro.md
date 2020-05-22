# Arm Mbed tutorials

The Arm Mbed ecosystem is expansive and offers many opportunities. In contrast to other sections of the documentation, which provide background reference material, this section provides instructions for specific tasks you may wish to perform. This section contains two formats of documentation: tutorials and examples. Tutorials include step-by-step guidance, and examples are code snippets you can use as a starting point for your application or as a reference on how to use a particular API.

## Getting started

<td><a href="../quick-start/index.html">Mbed OS quick start tutorial</a></td>

## RTOS APIs

| API | Examples | Tutorials |
| --- | --- | --- |
| ConditionVariable | [ConditionVariable example](../apis/rtos-apis.html#conditionvariable-example) | |
| EventFlags | [EventFlags example](../apis/eventflags.html#eventflags-example) | |
| IdleLoop | [IdleLoop example](../apis/idle-loop.html#example) |
| Kernel | [Example: get_ms_count()](../apis/kernel-interface-functions.html#get-ms-count-example)<br> [Example: hooks](../apis/kernel-interface-functions.html#kernel-hooks-example) | |
| Mail | [Mail example](../apis/mail.html#mail-example) | |
| Mutex | [Mutex example](../apis/mutex.html#mutex-example) | |
| Queue | [Queue example](../apis/queue.html#queue-example) <br> [Queue and MemoryPool](../apis/queue.html#queue-and-memorypool-example)| |
| Semaphore  | [Semaphore example](../apis/semaphore.html#semaphore-example) | |
| ThisThread | [ThisThread example](../apis/thisthread.html#thisthread-example) | |
| Thread | [Thread example](../apis/thread.html#thread-example)<br> [Thread example with callbacks](../apis/thread.html#thread-example-with-callbacks)<br> | |

## Event handling APIs

| API | Examples | Tutorials |
| --- | --- | --- |
| Event | [Posting events to the queue](../apis/event-handling-apis.html) |  |
| EventQueue | [Chaining events from more than one queue](../apis/eventqueue.html#eventqueue-example-chaining-events-from-more-than-one-queue)<br> [Deferring from interrupt context](../apis/eventqueue.html#eventqueue-example-deferring-from-interrupt-contextl) <br> [Posting events to the queue](../apis/eventqueue.html#eventqueue-example-posting-events-to-the-queue) <br> [Shared event: deferring from interrupt context](../apis/eventqueue.html#shared-event-example-running-the-shared-queue-from-main)<br>  [Shared event: running the shared queue from main](../apis/eventqueue.html#shared-event-example-running-the-shared-queue-from-main)<br> [Static event queue example](../apis/eventqueue.html#static-eventqueue-example-posting-user-allocated-events-to-the-static-queue) | [EventQueue tutorial](../apis/scheduling-tutorials.html)|
| UserAllocatedEvent | [Static event queue example](../apis/userallocatedevent.html#static-eventqueue-example-posting-user-allocated-events-to-the-queue) | |

## Serial (UART) Driver APIs

| API | Examples  | Hello, World |
| --- | ---  | --- |
| BufferedSerial | [BufferedSerial example](../apis/serial-uart-apis.html#bufferedserial-examples) | |
| UnbufferedSerial | [UnbufferedSerial example](../apis/unbufferedserial.html#unbufferedserial-example) | |

## SPI APIs

| API | Examples | Tutorials |
| --- | --- | --- |
| QuadSPI (QSPI) | [QuadSPI example](../apis/spi-apis.html#quadspi-example) | |
| SPI | | [SPI Hello, World](../apis/spi.html#spi-hello-world) |
| SPISlave | [SPISlave example](/apis/spislave.html#spislave-example) | |


## Input/Output (I/O) Driver APIs

| API | Examples  | Hello, World |
| --- | ---  | --- |
| AnalogIn | [AnalogIn example](../apis/i-o-apis.html#analogin-examples) | [AnalogIn Hello, World](../apis/i-o-apis.html#analogin-hello-world)|
| AnalogOut | [AnalogOut example](../apis/analogout.html#analogout-example) | [AnalogIn Hello, World](../apis/analogout.html#analogout-hello-world) |
| BusIn | | [BusIn Hello, World](../apis/busin.html#busin-hello-world) |
| BusOut | | [BusOut Hello, World](../apis/busout.html#busout-hello-world) |
| BusInOut | | [BusInOut Hello, World](../apis/businout.html#businout-hello-world) |
| DigitalIn | [DigitalIn exanple](../apis/digitalin.html#digitalin-example) | [DigitlaIn Hellw, World](../apis/digitalin.html#digitalin-hello-world) |
| DigitalOut | | [DigitalOut Hello, World](../apis/digitalout.html#digitalout-hello-world) |
| DigitalInOut | | [DigitalInOut Hello, World](../apis/digitalinout.html#digitalinout-hello-world) |
| InterruptIn | [InterruptIn example](../apis/interruptin.html#interruptin-example) | [InterruptIn Hello, World](../apis/interruptin.html#interruptin-hello-world) |
| PortIn | | [PortIn Hello, World](../apis/portin.html#portin-hello-world) |
| PortOut | | [PortOut Hello, World](../apis/portout.html#portout-hello-world) |
| PortInOut | | [PortInOut Hello, World](../apis/portinout.html#portinout-hello-world) |
| PwmOut | [PwmOut example](../apis/pwmout.html#pwmout-code-examples) | [PwmOut Hello, World](../apis/pwmout.html#pwmout-hello-world) |

## USB Driver APIs

| API | Examples | Tutorials |
| --- | --- | --- |
| USBAudio | [Sound data example](../apis/usb-apis.html#usbaudio-play-sound-data-example) <br> [Square wave example](../apis/usb-apis.html#usbaudio-square-wave-exampl) <br> [Loopback example](../apis/usb-apis.html#usbaudio-loopback-example) | [Audio player tutorial](../apis/usb-wav-audio-player.html) |
| USBCDC | [USBCDC example](../apis/usbcdc.html#usbcdc-example) | |
| USBCDC_ECM | [USBCDC_ECM example](../apis/usbcdc-ecm.html) | |
| USBHID | [USBHID example](../apis/usbhid.html#usbhid-example) | |
| USBKeyboard | [USBKeyboard example](../apis/usbkeyboard.html#usbkeyboard-example) | |
| USBMIDI | [USBMIDI example](../apis/usbmidi.html#usbmidi-example) <br> ["Take Me Out to the Ball Game" example](../apis/usbmidi.html#play-take-me-out-to-the-ball-game-example) | |
| USBMouse | [USBMouse example](../apis/usbmouse.html#usbmouse-example) <br> [Joystick example](../apis/usbmouse.html#usbmouse-joystick-example) | |
| USBMouseKeyboard | [USBMouseKeyboard](../apis/usbmousekeyboard.html#usbmousekeyboard-example) | |
| USBMSD | [USBMSD example](../apis/usbmsd.html#usbmsd-example) | |
| USBSerial | [USBSerial example](../apis/usbserial.html#usbserial-example) | |

## Other Driver APIs

| API | Examples | Tutorials |
| --- | --- | --- |
| CAN | | [CAN Hello, World](../apis/other-driver-apis.html#can-hello-world) |
| Flash IAP | [Flash IAP example](../apis/flash-iap.html#flash-iap-example) | |
| I2C | | [I2C Hello, World](../apis/i2c.html#i2c-hello-world) |
| I2CSlave | [I2CSlave example](../apis/i2cslave.html#i2cslave-example) | [I2C Hello, World](../apis/i2c.html#i2c-hello-world) |
| MbedCRC | [MbedCRC example](../apis/mbedcrc.html#mbedcrc-examples) | |
| ResetReason | [ResetReason example](../apis/resetreason.html) | |
| Watchdog | [Watchdog example](../apis/watchdog.html) | |

And the following tutorial:

- [Alarm](../apis/drivers-tutorials.html)

## Time Platform APIs

| API | Examples |
| --- | --- |
| RTC | [RTC example](../apis/time-apis.html#rtc-time-example) |
| Ticker | [Ticker example](../apis/ticker.html#ticker-examples) | [Ticker Hello, World](../apis/ticker.html#ticker-hello-world) |
| Time | [Time example](../apis/time.html#time-example) |
| Timeout | [Timeout example](../apis/timeout.html#timeout-example) | [Timeout Hello, World](../apis/timeout.html#timeout-hello-world) |
| Timer | | [Timer Hello, World](../apis/timer.html#timer-hello-world) |

And the following tutorial:

- [Application flow control](../apis/platform-tutorials.html)

## Power Platform APIs

| API | Examples |
| --- | --- |
| DeepSleepLock | [DeepSleepLock example](../apis/power-apis.html#example) |
| LowPowerTicker | [LowPowerTicker example](../apis/lowpowerticker.html#lowpowerticker-example) | |
| LowPowerTimeout | [LowPowerTimeout example](../apis/lowpowertimeout.html#lowpowertimeout-example) | |
| LowPowerTimer | [LowPowerTimer example](../apis/lowpowertimer.html#lowpowertimer-example) | |
| PowerManagement | [PowerManagement example](../apis/power-management-sleep.html#example) |

## Memory Platform APIs

| API | Examples |
| --- | --- |
| Memory tracing (mbed_mem_trace) | [Memory tracing example](../apis/memory-apis.html#memory-tracing-example) |
| MPU management (mpug_mgmt) | [MPU management example](../apis/mpu-management.html#example) |
| MemoryPool | [MemoryPool example](../apis/memorypool.html#memorypool-example) | |
| Mbed statistics  (mbed_stats)| [Memory statistics example](../apis/mbed-statistics.html#memory-statistics-example) <br> [Thread statistics example](../apis/mbed-statistics.html#thread-statistics-example) <br> [System information example](../apis/mbed-statistics.html#system-information-example) <br> [CPU statistics example](../apis/mbed-statistics.html#cpu-statistics-example)|

## Other Platform APIs

| API | Examples |
| --- | --- |
| Assert | [Assert example](../apis/other-platform-apis.html#assert-example) |
| ATCmdParser | [ATCmdParser example](../apis/atcmdparser.html#atcmdparser-examples) |
| Callback | [Serial passthrough example](../apis/callback.html#serial-passthrough-example-with-callbacks)<br> [Thread example](../apis/callback.html#thread-example-with-callbacks)<br> [Sonar example](../apis/callback.html#sonar-example) |
| CircularBuffer | [CircularBuffer example](../apis/circularbuffer.html#circularbuffer-example) |
| CriticalSectionLock | [CriticalSectionLock example](../apis/criticalsectionlock.html#criticalsectionlock-example) |
| Debug | [Debug example](../apis/debug.html#debug-example) |
| Error handling | [Error handling example](../apis/error-handling.html#error-handling-example)<br> [Crash reporting example](../apis/error-handling.html#crash-reporting-example) |
| FileHandle | [C library example](../apis/filehandle.html#filehandle-using-c-library-example)<br> [Sigio example](../apis/filehandle.html#filehandle-sigio-example) |
| NonCopyable | [NonCopyable example](../apis/noncopyable.html#noncopyable-example) |
| PlatformMutex | [PlatformMutex example](../apis/platformmutex.html#platformmutex-example) |
| Poll | [Poll example](../apis/poll.html#poll-example) |
| ScopedRamExecutionLock | [ScopedRamExecutionLock](../apis/scopedramexecutionlock.html#example) |
| ScopedRomWriteLock | [ScopedRomWriteLock example](../apis/scopedromwritelock.html#scopedromwritelock-class-reference) |
| SharedPtr | [Shared pointer example](../apis/shared-pointer.html#shared-pointer-example) |
| Span | [Span example](../apis/span.html#span-example) |

## File system APIs

| API | Examples |
| --- | --- |
| FileSystem | [FileSystem example](../apis/filesystem.html#file-system-example) |
| KVStore | [KVStore example](../apis/kvstore.html#kvstore-example) |

## BlockDevice APIs

| API | Examples |
| --- | --- |
| BlockDevice | [BlockDevice example](../apis/blockdevice-apis.html#blockdevice-example) |
| BufferedBlockDevice | [BufferedBlockDevice example](../apis/bufferedblockdevice.html#bufferedblockdevice-example) |
| ChainingBlockDevice | [ChainingBlockDevice example](../apis/chainingblockdevice.html#chainingblockdevice-example) |
| DataFlashBlockDevice | [DataFlashBlockDevice example](../apis/dataflashblockdevice.html#dataflashblockdevice-example) |
| FlashIAPBlockDevice | [FlashIAPBlockDevice example](../apis/flashiapblockdevice.html#flashiapblockdevice-example) |
| FlashSimBlockDevice | [FlashSimBlockDevice example](../apis/flashsimblockdevice.html#flashsimblockdevice-example) |
| HeapBlockDevice | [HeapBlockDevice example](../apis/heapblockdevice.html#heapblockdevice-example) |
| MBRBlockDevice | [MBRBlockDevice example](../apis/mbrblockdevice.html#mbrblockdevice-example) |
| ProfilingBlockDevice | [ProfilingBlockDevice example](../apis/profilingblockdevice.html#profilingblockdevice-example) |
| QSPIFBlockDevice | [QSPIFBlockDevice example](../apis/qspifblockdevice.html#qspifblockdevice-example) |
| SDBlockDevice | [SDBlockDevice example](../apis/sdblockdevice.html#sdblockdevice-example-application) |
| SlicingBlockDevice | [SlicingBlockDevice](../apis/slicingblockdevice.html#slicingblockdevice-example) |
| SPIFBlockDevice | [SPIFBlockDevice example](../apis/spi-flash-block-device.html#spifblockdevice-example) |

## Network socket APIs

| API | Examples | Tutorials |
| --- | --- | --- |
| Non-IP cellular socket | [Non-IP cellular socket example](../apis/network-socket-apis.html#cellularnonipsocket-example) | |
| Socket | [Socket example](../apis/socket.html#socket-example) | |
| SocketAddress | [SocketAddress example](../apis/socketaddress.html#socketaddress-example) | |
| SocketStats | [SocketStats example](../apis/socketstats.html#socketstats-example) | |
| TCPSocket | [TCPSocket example](../apis/tcpsocket.html#tcpsocket-example) | |
| UDPSocket | [UDPSocket example](../apis/udpsocket.html#udpsocket-example) | |

## Network interfaces APIs

| API | Examples | Tutorials |
| --- | --- | --- |
| Cellular | [Cellular example](../apis/network-interface-apis.html#cellular-example-connection-establishment) | |
| EthInterface | [EthInterface example](../apis/ethernet.html#ethinterface-example) | |
| Network status | [Network status example](../apis/network-status.html#example) | |
| Wi-Fi | [Wi-Fi example](../apis/wi-fi.html#wi-fi-example) | |

## Secure socket APIs

| API | Examples | Tutorials |
| --- | --- | --- |
| DTLSSocket | [DTLSSocket example](../apis/secure-socket-apis.html#dtlssocket-example) | |
| TLSSocket | [TLSSocket example](../apis/tlssocket.html#tlssocket-example) | [Secure communication tutorial](../apis/tls-tutorial.html) |

## DNS API

| API | Examples | Tutorials |
| --- | --- | --- |
| DNS Resolver | [DNS Resolver example](../apis/dns-apis.html#dns-resolver-example) | |

## Bluetooth (BLE) APIs

We have placed all of our BLE examples in a single [GitHub repository](https://github.com/ARMmbed/mbed-os-example-ble).

## NFC APIs

| API | Examples |
| --- | --- |
| MessageBuilder | [MessageBuilder example](../apis/nfc-apis.html#messagebuilder-example) |
| MessageParser | [MessageParser example](../apis/messageparser.html#messageparser-example) || Mesh | | [Mesh tutorial](../apis/connectivity-tutorials.html) <br>  [Light control tutorial](../apis/light-control.html) |
| NFCController | [NFCController example](../apis/nfccontroller.html#nfccontroller-example) |
| NFCEEPROM | [NFCEEPROM example](../apis/nfc-eeprom.html#nfceeprom-example) |
| SimpleMessageParser | [SimpleMessageParser example](../apis/simplemessageparser.html#simplemessageparser-example) |


## LoRa APIs

A [private network tutorial](../apis/LoRa-tutorial.html).


## Security APIs

You can try the following examples on GitHub:

- [TLS client](https://github.com/ARMmbed/mbed-os-example-tls/blob/master/tls-client): Downloads a file from an HTTPS server (os.mbed.com) and looks for a specific string in that file.

- [Benchmark](https://github.com/ARMmbed/mbed-os-example-tls/blob/master/benchmark): Measures the time taken to perform basic cryptographic functions used in the library.

- [Hashing](https://github.com/ARMmbed/mbed-os-example-tls/blob/master/hashing): Demonstrates the various APIs for computing hashes of data (also known as message digests) with SHA-256.

- [Authenticated encryption](https://github.com/ARMmbed/mbed-os-example-tls/blob/master/authcrypt): Demonstrates using the Cipher API for encrypting and authenticating data with AES-CCM.

Each of them comes with complete usage instructions as a readme file in the repository.

- Or try [DeviceKey](../apis/security-apis.html#devicekey-example).


## Serial communication

These tutorials teach you to communicate with your development board, an essential part of programming and debugging:

- [Windows serial driver tutorial](../program-setup/windows-serial-driver.html)
- [Board to PC communication over USB tutorial](../program-setup/serial-communication.html)
- [Low memory serial printf example](../program-setup/serial-communication.html#minimal-printf)

## Debugging

These tutorials show you how to install, export a project to and start a debugging session with different IDEs.

### Methods

- [BBC micro:bit, pyOCD and GDB debugging tutorial](../debug-test/debug-microbit.html).
- [Troubleshooting common issues](../debug-test/troubleshooting-common-issues.html).
- [Analyzing Mbed OS crash dump tutorial](../debug-test/analyzing-mbed-os-crash-dump.html).
- [Compile time errors tutorial](../debug-test/compile-time-errors.html).
- [Debugging using `printf` statements](../debug-test/debugging-using-printf-statements.html).
- [Error handling API example](../apis/error-handling.html#error-handling-example)

### Debugging with third party tools

- [Eclipse](../debug-test/third-party-tools.html).
- [Keil uVision](../debug-test/keil-uvision.html).
- [Visual Studio](../debug-test/visual-studio-code.html).


## Bootloader

A [tutorial for creating and using a bootloader](../program-setup/creating-and-using-a-bootloader.html), and [an example bootloader](https://github.com/ARMmbed/mbed-os-example-bootloader).

## Optimizing

<table>
<tbody>
<tr>
<td><a href="optimizing.html">Memory optimizations tutorial</a></td>
<td><a href="../apis/mbed-statistics.html#thread-statistics-example">Thread statistics example</a></td>
<td><a href="../apis/mbed-statistics.html#cpu-usage-example">CPU usage example</a></td>
<td><a href="power-optimization.html">Power optimization tutorial</a></td>
</tr>
<tr>
<td><a href="../apis/mbed-statistics.html#system-information-example">System information example</a></td>
<td><a href="../apis/mbed-statistics.html#cpu-statistics-example">CPU statistics example</a></td>
</tr>
</tbody>
</table>

## Migrating

If you are moving from Mbed OS 5 to Mbed OS 6, please see [the list of deprecated APIs](../apis/index.html#deprecated-apis).

If you are moving from Mbed 2 to Mbed OS 6 bare metal, [please see the bare metal documentation](../bare-metal/index.html).

## Setting up

### Hardware setup

Porting Mbed OS requires the following hardware:

- A development PC. You can port targets, connectivity and storage on Windows, macOS or Linux. However, due to limitations in some development tools that Mbed OS uses, you need a Windows PC for DAPLink/FlashAlgo development.
-  An evaluation board with a target MCU, debug probe or an integrated interface chip.

    The new target needs a unique board ID. To get one, please contact your technical account manager or email [our support team](mailto:support@mbed.com) to get one.

- A storage device (SD or external flash).
- A micro SD card for the CI test shield.
- A micro USB cable to connect the evaluation board to your development PC.

You may also need:

- If the interface MCU is not on the evaluation board, choose a debug probe, such as [SDWAP-LPC11U35](https://os.mbed.com/platforms/SWDAP-LPC11U35/). You will then need a micro USB cable (in addition to the micro USB cable listed above).
- An FTDI TTL232R-3V3 USB cable, for the Tx and Rx pins of debug probes that do not have a serial connection.

The following items might help you test SPI, I2C and Pins:

- A CI test shield v2.0.0. For details, refer to [https://github.com/ARMmbed/ci-test-shield](https://github.com/ARMmbed/ci-test-shield).

<span class="tips">Check the user guide of the evaluation board to see if anything needs to be done prior to using a debug probe and running Mbed OS programs.</span>

### Software setup

Please install the following:

- [Python 2.7](https://www.python.org/downloads/release/python-2715/).
- [Git](https://git-scm.com/downloads).
- [Mbed CLI](../tools/installation-and-setup.html).
- Choose an IDE and debugger. The three commonly used IDEs are [Eclipse](https://www.eclipse.org/ide/), [IAR Embedded Workbench](https://www.iar.com/iar-embedded-workbench/) and [Keil MDK](http://www.keil.com/).

    Limitations:

    - Eclipse is license free, whereas both IAR and Keil IDE require licenses.
    - Currently, DAPLink development works only Keil MDK. You will have to use Keil for pyOCD and DAPLink development.

- (Optional) [FTDI serial driver](http://www.ftdichip.com/Drivers/VCP.htm).

<span class="notes">The [tools documentation](../tools/index.html) contains the exact third party tool versions supported in a specific Mbed OS release.</span>

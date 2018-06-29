<h2 id="quick-start-offline">Offline - Arm Mbed CLI</h2>

### Setup

The setup process for Arm Mbed CLI depends on your operating system. Please choose your host operating system. The setup instructions for each operating system walk you through how to install Mbed CLI locally. 

[**Windows**](#windows) | [**Mac OS X**](#mac-os-x) | [**Linux**](#linux)

#### Windows

Two installation methods are available for Windows. The first is a prebuilt installer that you can use quickly. The second installation method is more flexible and allows for greater customization to better fit your system's needs.

##### Prebuilt Mbed CLI installer

Download and run the [Mbed CLI Windows .exe installer](https://mbed-media.mbed.com/filer_public/50/38/5038849b-16a8-42f3-be7a-43d98c7a3af3/mbed_installer_v043.exe).

You can ensure Mbed CLI installed correctly by running `mbed help` from your command-line.

<span class="notes">**Note:** The Windows installer only installs the GNU Arm embedded toolchain. If you want to compile using Arm Compiler 5 or IAR, visit the [supported compilers page](/docs/latest/tools/index.html#compiler-versions).</span>

#### Manual installation

###### 1. Download and install Python and Pip

Download and install [Python versions 2.7.11 or 3.6.5](https://www.python.org/downloads/windows/) or later for Windows. Both Python versions come with their own version of Pip.

<span class="notes">**Note:** When the installer launches, check the checkbox that says **Add Python X.Y to PATH**. Otherwise, Windows does not know where to search for the Python executable.</span>

###### 2. Install a compiler

Download and install a compiler.

<span class="notes">**Note:** To download the latest toolchains, visit the [supported compilers page](/docs/development/tools/index.html#compiler-versions).</span>

###### 3. Install Mbed CLI

To install Mbed CLI, run `pip install mbed-cli` from your command-line.

You can ensure Mbed CLI installed correctly by running `mbed --version`.

##### 2. Setup environment

After installation is complete, be sure to add any available toolchains to Mbed CLI's global configuration. Below is an example using the ARM compiler:

```
> mbed config -G ARM_PATH <path to ARM bin\>"
[mbed] <path to ARM bin\> now set as global ARM_PATH

> mbed config --list
[mbed] Global config:
ARM_PATH=<path to ARM bin\>

```

<span class="notes">**Note:** You can also apply the same configuration to the IAR and GNU toolchains using `IAR_PATH` or `GCC_ARM_PATH`.</span>

#### Mac OS X

##### 1. Install Python and Pip

Mac OS X 10.8+ comes with Python 2.7 preinstalled by Apple. If you are running an earlier version of Mac OS X, download and install [Python versions 2.7.11 or 3.6.5](https://www.python.org/downloads/mac-osx/) or later.

To install Pip, run `sudo easy_install pip` from your command-line.

##### 2. Install a compiler

Download and install a compiler.

<span class="notes">**Note:** To download the latest toolchains, visit the [supported compilers page](/docs/latest/tools/index.html#compiler-versions).</span>

##### 3. Install Mbed CLI

To install Mbed CLI, run `pip install mbed-cli` from your command-line.

You can ensure Mbed CLI installed correctly by running `mbed --version`.

##### 4. Setup environment

For any installed toolchain, be sure to add the Mbed CLI global configuration:

```
$ mbed config -G ARM_PATH <path to ARM bin\>"
[mbed] <path to ARM bin\> now set as global ARM_PATH

$ mbed config --list
[mbed] Global config:
ARM_PATH=<path to ARM bin\>

```

<span class="notes">**Note:** You can also apply the same configuration to the IAR and GNU toolchains using `IAR_PATH` or `GCC_ARM_PATH`.</span>

#### Linux

##### 1. Install Python and Pip

Download and install [Python versions 2.7.11 or 3.6.5](https://www.python.org/downloads/source/) or later, or use your distribution's package manager to install Python and Pip.

As an example, you can use the following in Ubuntu:

```console
$ sudo apt-get install python2.7 python-pip
```

##### 2. Install a compiler

Download and install a compiler:

<span class="notes">**Note:** To download the latest toolchains, visit the [supported compilers page](/docs/latest/tools/index.html#compiler-versions).</span>

##### 3. Install Mbed CLI

To install Mbed CLI, run `pip install mbed-cli` from your command-line.

You can ensure Mbed CLI installed correctly by running `mbed help`.

##### 4. Setup environment

For any installed toolchain, be sure to add the Mbed CLI global configuration:

```
$ mbed config -G ARM_PATH <path to ARM bin\>"
[mbed] <path to ARM bin\> now set as global ARM_PATH

$ mbed config --list
[mbed] Global config:
ARM_PATH=<path to ARM bin\>

```

<span class="notes">**Note:** You can also apply the same configuration to the IAR and GNU toolchains using `IAR_PATH` or `GCC_ARM_PATH`.</span>

### Code

#### 1. Get the code

From your command-line, import the example:

```console
$ mbed import https://github.com/ARMmbed/mbed-os-example-blinky
$ cd mbed-os-example-blinky
```

#### 2. Compile and program board

Invoke `mbed compile`, and specify the name of your platform and your installed toolchain (`GCC_ARM`, `ARM`, `IAR`). For example, for the K64F platform and Arm Compiler 5 toolchain:
  
```console
$ mbed compile --target K64F --toolchain ARM --flash
```  

The `--flash` argument automatically flashes the compiled program onto your board if it is connected to your computer. You can see which boards are connected with `mbed detect`.

After you have flashed the program to the board, press the board's reset button. The LED blinks.

<span class="notes">**Note:** You can get the name of the board plugged into your computer by running `mbed detect`, and you can get a full list of supported toolchains and targets by running the `mbed compile --supported` command.</span>

### Debug

#### Desktop IDE

To debug using a desktop IDE such as Keil uVision, IAR or Eclipse, use the `mbed export` command to generate project files. For example, for a K64F and Keil uVision:

```console
$ mbed export --ide uvision --target K64F
```  

<span class="notes">**Note:** For a full list of supported exporters, run the `mbed export --supported` command.</span>

#### Printf

Another way to do basic debugging is to use the `printf` command in your code and read the output using a serial terminal, such as [PuTTY](http://www.putty.org/) or [CoolTerm](http://freeware.the-meiers.org/). For example, add `printf("Hello World!\n\r");` to the top of your main function, and then recompile the program and flash it to your device.

Invoke `mbed detect` from your command-line to determine which communication port your board connects to (in other words, `COM18`, `/dev/ttyACM0` and so on). Unless otherwise specified, `printf` defaults to a baud rate of `9600` on Mbed OS.

### Further reading

More examples:
- [Mbed OS examples](https://os.mbed.com/teams/mbed-os-examples/code/) - list of Mbed OS 5 example repositories.

- Documentation
  - [Mbed OS APIs](https://os.mbed.com/docs/latest/reference/apis.html) - list of all APIs available in Mbed OS.
  - [Peripheral drivers](https://os.mbed.com/docs/latest/reference/drivers.html) - IO driver APIs (I2C, SPI, UART and so on).

- Tutorials
  - [Advanced debugging](https://os.mbed.com/docs/latest/tutorials/debugging.html).
  - [Serial communications](https://os.mbed.com/docs/latest/tutorials/serial-communication.html).
  - [Optimizing binary size](https://os.mbed.com/docs/latest/tutorials/optimizing.html).

- Other resources
  - [Components database](https://os.mbed.com/components/) - libraries and example code for various hardware and software components.
  - [Mbed OS forum](https://os.mbed.com/forum/) - a resource of questions and answers and an active user community. Ask your questions here first.
  - [Youtube channel](http://youtube.com/armmbed) - videos and workshop content.

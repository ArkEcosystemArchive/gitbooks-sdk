# Installation

## C++ installation

[Windows](https://docs.microsoft.com/en-us/cpp/build/vscpp-step-0-installation?view=vs-2019)

[Unix](https://linuxconfig.org/how-to-install-g-the-c-compiler-on-ubuntu-18-04-bionic-beaver-linux)

For OSx you can use `brew` to install `gcc` by doing so : `brew install gcc`

## CMake

> CMake is an open-source, cross-platform family of tools designed to build, test and package software. CMake is used to control the software compilation process using simple platform and compiler independent configuration files, and generate native makefiles and workspaces that can be used in the compiler environment of your choice.

### Install package with CMake

Head over to [cmake.org](https://www.cmake.org/download/) or install it via Homebrew `brew install cmake`.

Once CMake properly installed, you can now install the package.

```bash
git clone https://github.com/ARKEcosystem/cpp-crypto
cd cpp-crypto
# Init & Update Micro-Ecc Submodule
git submodule init
git submodule update
cmake .
cmake --build .
```

## Arduino

> Arduino is an open-source electronics platform based on easy-to-use hardware and software. It's intended for anyone making interactive projects.

### Install package for Arduino

Download and install the Arduino IDE \(&gt;=1.8.5\) from [arduino.cc](https://www.arduino.cc/en/Main/Software)

Using the Arduino IDE's built-in Library Manager, install the ARK-Cpp-Crypto library. Be sure to install the "-arduino" version of Cpp-Crypto.

#### Dependencies

Using the Arduino IDE's built-in Library Manager, also install the following libraries:

* micro-ecc
* ArduinoJson@5.13.5

### Using With the Arduino IDE

Include the following header in your Arduino Sketch:

```cpp
#include <arkCrypto.h>
```

## PlatformIO

> An open source ecosystem for IoT development. Cross-platform IDE and unified debugger. Remote unit testing and firmware updates.

### Install package for PlatformIO

Python is required to run PlatformIO, so grab an installer package from [python.org](https://www.python.org/downloads/).

Head over to [platformio.org](https://platformio.org/install) to learn how to install PlatformIO.

Once installed, add the following line to your `platformio.ini` configuration file:

```text
lib_deps = ARK-Cpp-Crypto
```

This is an example of a fully configured \`platformio.ini file for the Adafruit ESP32 Feather:

```text
; PlatformIO Project Configuration File
;
;   Build options: build flags, source filter
;   Upload options: custom upload port, speed and extra flags
;   Library options: dependencies, extra library storages
;   Advanced options: extra scripting
;
; Please visit documentation for the other options and examples
; https://docs.platformio.org/page/projectconf.html

[env:featheresp32]platform = espressif32
board = featheresp32
framework = arduino
lib_deps = ARK-Cpp-Crypto
upload_speed = 921600
monitor_speed = 115200
```


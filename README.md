# armor-gui

## How to build binaries from source code

### Windows
To build the gui you must have built armor core, so please do all steps from [here](https://github.com/Armor-Network/armor#building-on-windows) before proceeding!
<br/>Install [QtCreator](https://www.qt.io/download-thank-you?os=windows), open the project file armor-gui/src/armor-gui.pro in QtCreator and build it using MSVS kit (you must have MSVS installed already to build armor core).

Detailed build instructions for armor-gui [here](https://github.com/kbhse/armor-gui/blob/main/DetailedBuild.md#building-the-armor-gui-wallet-for-windows-from-source-code).

### MacOS

To build the gui you must have built armor core, so please do all steps from [here](https://github.com/Armor-Network/armor#building-on-mac-osx) before proceed. Install [QtCreator](https://www.qt.io/download-thank-you?os=macos), open the project file armor-gui/src/armor-gui.pro in QtCreator and build it using clang kit (you must have XCode installed already to build armor core).

### Linux
```
# To install all required packages on Ubuntu use the following command:
$ sudo apt install qt5-qmake qtbase5-dev qtbase5-dev-tools

$ git clone https://github.com/Armor-Network/armor.git
$ cd armor
$ mkdir -p build
$ cd build
$ cmake ..
$ make -j4 armor-crypto
$ cd ../..
$ git clone https://github.com/Armor-Network/armor-gui.git
$ cd armor-gui
$ mkdir -p build
$ cd build
$ cmake ..
$ make -j4
```
Alternative way:
```
# Install QtCreator:
$ sudo apt install qtcreator

$ git clone https://github.com/Armor-Network/armor.git
$ cd armor
$ mkdir -p build
$ cd build
$ cmake ..
$ make -j4 armor-crypto
$ cd ../..
$ git clone https://github.com/Armor-Network/armor-gui.git
```
Now open the project file armor-gui/src/armor-gui.pro in QtCreator and build it.

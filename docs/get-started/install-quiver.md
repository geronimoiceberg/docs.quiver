description: Install Quiver
<!--- END of page meta data -->

# Install Quiver

Install Quiver by using the [installers](#using-installers) or [compiling from source](#compiling-from-source).

## Using installers

### MacOS

1. [Download the latest release](https://github.com/Arrowchain/arrowwallet/releases).
1. Double-click the `.dmg` file, and drag the Quiver icon into the Applications folder.

### Windows

1. [Download the latest release](https://github.com/Arrowchain/arrowwallet/releases).
1. Unpack the `.zip` file, and double-click `quiver.exe`.

### Linux

If you use the Debian or Ubuntu operating system, [use the `.deb` package](#use-the-deb-package). Otherwise, [run the binaries](#run-the-binaries).

#### Use the `.deb` package

Run the following commands in a terminal window:

```
sudo dpkg -i linux-deb-quiver-0.1.8.deb
sudo apt install -f
```

#### Run the binaries

Run the following commands in a terminal window:

```
tar -xvf quiver-v0.1.8.tar.gz
./quiver-v0.1.8/quiver
```

## Compiling from source

#### Prerequisites

* [Qt V5.11 or later releases](https://www.qt.io/download)
* C++ compiler for your platform
* Platform-specific prerequisites:
    * MacOS: [Xcode](https://developer.apple.com/xcode/) or [Xcode command line tools](https://developer.apple.com/downloads/index.action)
    * Windows: [Microsoft Visual Studio](https://visualstudio.microsoft.com/vs/whatsnew/)
    * Linux: Mesa

#### MacOS

In a terminal window, run the following commands:

```
git clone https://github.com/Arrowchain/arrowwallet.git
cd arrowwallet
/path/to/qt5/bin/qmake zec-qt-wallet.pro CONFIG+=debug
make

./quiver.app/Contents/MacOS/quiver
```

#### Windows

From the Visual Studio command prompt, run the following commands:

```
git clone https://github.com/Arrowchain/arrowwallet.git
cd arrowwallet
c:\Qt5\bin\qmake.exe zec-qt-wallet.pro -spec win32-msvc CONFIG+=debug
nmake

debug\quiver.exe
```

#### Linux

In a terminal window, complete the following steps:

1. Install Mesa.

    ```
    sudo apt install libgl1-mesa-dev
    ```

1. Clone the Quiver repository and run the build.

    ```
    git clone https://github.com/Arrowchain/arrowwallet.git
    cd zecwallet
    /path/to/qt5/bin/qmake zec-qt-wallet.pro CONFIG+=debug
    make -j$(nproc)

    ./quiver
    ```

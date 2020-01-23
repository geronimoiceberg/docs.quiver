description: Compile arrowd
<!--- END of page meta data -->

# Compile arrowd


### System requirements:

2 or more CPU threads  
64-bit OS  
4GB+ RAM  
20GB+ storage  

## Build for Linux from source

### Install Ubuntu/Debian dependencies

```
sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install build-essential pkg-config libc6-dev m4 g++-multilib autoconf libtool ncurses-dev unzip git python python-zmq zlib1g-dev wget curl bsdmainutils automake
```
### Install Fedora dependencies (if using Fedora/CentOS 8 or an alternative)
```
sudo dnf install git pkgconfig automake autoconf ncurses-devel python python-zmq wget gtest-devel gcc gcc-c++ libtool curl patch
```

### Install CentOS dependencies (if using CentOS 7 or lower)
```
sudo yum install git pkgconfig automake autoconf ncurses-devel python python-zmq wget gtest-devel gcc gcc-c++ libtool curl patch
```

### Build arrowd

```
git clone https://github.com/Arrowchain/arrow.git
cd arrow
./zcutil/build.sh -j$(nproc)
```

### Create config file
  * Replace `{username}` with your preferred RPC username
```
mkdir ~/.arrow
echo "rpcuser={username}" >> ~/.arrow/arrow.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.arrow/arrow.conf
echo "rpcallowip=127.0.0.1" >> ~/.arrow/arrow.conf
echo "addnode=52.90.76.26:7654" >> ~/.arrow/arrow.conf
echo "addnode=45.77.143.128:7654" >> ~/.arrow/arrow.conf
echo "addnode=85.15.179.171:7654" >> ~/.arrow/arrow.conf
echo "addnode=65.100.172.203:7654" >> ~/.arrow/arrow.conf
echo "addnode=34.204.183.163:7654" >> ~/.arrow/arrow.conf
```

### Fetch params

```
cd arrow
./zcutil/fetch-params.sh
```

### Run arrowd

```
./src/arrowd
```

## Build for MacOS from source

### Install dependencies

```
xcode-select --install
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install cmake autoconf libtool automake coreutils pkgconfig gmp wget
brew install gcc5 --without-multilib
```
### Build

```
git clone https://github.com/Arrowchain/arrow.git arrow
cd arrow
./zcutil/build.sh -j$(sysctl -n hw.ncpu)
```

### Fetch params

``` 
./zcutil/fetch-params.sh
```

### Create config file
  * Replace `{username}` with your preferred RPC username
```
mkdir ~/Library/Application Support/arrow/
echo "rpcuser={username}" >> ~/Library/Application Support/arrow/arrow.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/Library/Application Support/arrow/arrow.conf
echo "rpcallowip=127.0.0.1" >> ~/Library/Application Support/arrow/arrow.conf
echo "addnode=52.90.76.26:7654" >> ~/Library/Application Support/arrow/arrow.conf
echo "addnode=45.77.143.128:7654" >> ~/Library/Application Support/arrow/arrow.conf
echo "addnode=85.15.179.171:7654" >> ~/Library/Application Support/arrow/arrow.conf
echo "addnode=65.100.172.203:7654" >> ~/Library/Application Support/arrow/arrow.conf
echo "addnode=34.204.183.163:7654" >> ~/Library/Application Support/arrow/arrow.conf
```

### Run arrowd
``` 
./src/arrowd
```
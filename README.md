# Kiire-Linux-wallet-compiling-instructions
Compile a wallet for Ubuntu Linux on Ubuntu Server

**Update your Ubuntu server with the following command:**

sudo apt-get update && sudo apt-get upgrade -y

**Install the required dependencies with the following command:**

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3 curl libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-test-dev libboost-thread-dev libboost-all-dev libboost-program-options-dev libminiupnpc-dev libzmq3-dev libgmp3-dev libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler libqrencode-dev unzip doxygen cmake nsis wine-stable wine64 bc -y

**Install the repository ppa:bitcoin/bitcoin with the following command:**

sudo add-apt-repository ppa:bitcoin/bitcoin

**Confirm the installation of the repository by pressing on the enter key.**

**Install Berkeley DB with the following command:**

sudo apt-get update && sudo apt-get install libdb4.8-dev libdb4.8++-dev -y

**Create your source code directory with the following commands:**

cd ~/
mkdir source_code
cd source_code

**Download the source code of your coin with the following command:**

wget "https://dl.walletbuilders.com/download?customer=306750840041c9be1167434aeb430983b2997fd92a13db034f&filename=kiire-source.tar.gz" -O kiire-source.tar.gz

**Type the following command to extract the tar file:**

tar -xzvf kiire-source.tar.gz

**64-bit**

**Build x86_64-w64-linux with the following commands:**

PATH=$(echo "$PATH" | sed -e 's/:\/mnt.*//g')
cd depends
make HOST=x86_64-w64-linux
cd ..

**Type the following commands to compile your wallet for Ubuntu Linux.**

./autogen.sh
CONFIG_SITE=$PWD/depends/x86_64-w64-linux/share/config.site ./configure --prefix=/
make

**Type the following command to clean your source code:**

make clean

**32-bit**

**Build i686-w64-linux with the following commands:**

PATH=$(echo "$PATH" | sed -e 's/:\/mnt.*//g')
cd depends
make HOST=i686-w64-linux
cd ..

**Type the following commands to compile your wallet for Ubuntu Linux.**

./autogen.sh
CONFIG_SITE=$PWD/depends/i686-w64-linux/share/config.site ./configure --prefix=/
make

**The compiled wallet for Ubuntu Linux is located in the directory src/qt, the tools are located in the directory src.**

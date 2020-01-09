# Libtorrent Workshop

## Build libtorrent python bindings


Needed :

Linux
```
$ sudo apt install autoconf automake libtool libboost-all-dev libssl-dev build-essential python3-dev
```

macOS
```
$ brew update
$ brew install autoconf automake libtool openssl boost boost-python
$ xcode-select --install
```
BUILD:
```
$ git clone https://github.com/arvidn/libtorrent.git
$ cd libtorrent
$ ./autotool.sh
$ ./configure --enable-python-binding
$ make -j $(nproc)
```

or for macOS :
```
$ ./bootstrap.sh --with-openssl=/usr/local/opt/openssl --enable-python-binding
$ make -j$(sysctl -n hw.ncpu)
```

## Install Ubuntu

```
$ sudo apt install python3-libtorrent
```

## Install macOS

```
$ brew install libtorrent-rasterbar
```

## Using conan

```
$ conan remote add libtorrent https://api.bintray.com/conan/rllola80/Libtorrent
$ conan install --build=missing .
$ conan build .
$ python test.py
```

# Build Webkit on Amazon Linux 2

### Install dependency

```
yum install perl-version perl-Data-Dumper perl-core python3 automake libtool ninja-build bind-devel gcc-c++ openssl-devel ruby cairo cairo-devel harfbuzz harfbuzz-devel libjpeg-turbo-devel libepoxy-devel -y
yum install "perl(XML::LibXML)" -y
amazon-linux-extras install epel
```

### Install cmake

```
wget https://github.com/Kitware/CMake/releases/download/v3.17.0-rc3/cmake-3.17.0-rc3.tar.gz
tar -zxvf cmake-3.17.0-rc3.tar.gz
cd cmake-3.17.0-rc3/
./bootstrap #--prefix=/usr/local
make
make install
```

### Install libepoxy

```
wget https://github.com/anholt/libepoxy/releases/download/1.5.4/libepoxy-1.5.4.tar.xz
tar xf libepoxy-1.5.4.tar.xz
cd libepoxy-1.5.4.tar.xz/
mkdir _build && cd _build
pip3 install meson
pip3 install ninja
sudo ninja install
```

Stuck from here, even when remove and install newest libepoxy, webkit build still found older version.

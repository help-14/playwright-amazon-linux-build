# Build Firefox on Amazon Linux 2

- Creat a powerful VM on AWS, build will need lots of disk space and build time.
- SSH to VM then go to root: 
```
sudo su -
yum update
```

### Install rust
```
amazon-linux-extras install -y rust1
```

### Install nasm 2.13
```
cd /opt
wget http://www.nasm.us/pub/nasm/releasebuilds/2.13.01/nasm-2.13.01.tar.xz
tar -xf nasm-2.13.01.tar.xz
cd nasm-2.13.01
./configure --prefix=/usr && make && make install
```

### Install autoconf 2.13
```
cd ~/
wget http://ftp.gnu.org/gnu/autoconf/autoconf-2.13.tar.gz
tar -zvxf autoconf-2.13.tar.gz
cd autoconf-2.13
./configure && make
make install
ln -s /usr/local/bin/autoconf /usr/local/bin/autoconf-2.13
```

### Install dependency
```
yum install clang pulseaudio-libs-devel gtk3-devel pygobject2 glib2 dbus-glib-devel gtk2-devel pango-devel libdrm-devel libxkbcommon-devel yasm libXt-devel -y
cargo install cbindgen
```

### Install clang, llvm
```
amazon-linux-extras install -y epel
yum install -y bison cmake3 flex git iperf libstdc++-static python-netaddr gcc gcc-c++ zlib-devel elfutils-libelf-devel
yum install -y luajit luajit-devel
yum install -y http://repo.iovisor.org/yum/extra/mageia/cauldron/x86_64/netperf-2.7.0-1.mga6.x86_64.rpm
yum install -y python2-pyroute2
yum install -y clang clang-devel llvm llvm-devel llvm-static ncurses-devel
```

### Install nodejs 
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.2/install.sh | bash
source ~/.bashrc
nvm install 12.16.1
```

### Follow Playwright guide to build browser
- Clone Playwright repo
- Go to repo folder
- Run these command:
```
./browser_patches/prepare_checkout.sh firefox
cd ./browser_patches/firefox
./build.sh
```
Guide in [here](https://github.com/microsoft/playwright/tree/master/browser_patches)

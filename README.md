# Source codes of latest WCH OpenOCD

This repo is the newest source (2024-11-26) of WCH OpenOCD.

- work with all known WCH-LinkE debuggers, include WCH-LinkE r0 1v2 / r0 1v3.
- support program / debug all WCH ch32v/x/l series MCUs.

## Installation

```
./bootstrap
./configure --prefix=/opt/wch-openocd --enable-wlinke --disable-ch347 --disable-linuxgpiod --disable-werror --program-prefix=wch-
make
sudo make install
```

After installation successfully, please add `/opt/wch-openocd/bin` to your PATH env.

## Usage

```
wch-openocd -f /opt/wch-openocd/share/openocd/scripts/target/wch-riscv.cfg

```

You may copy `wch-riscv.cfg` to your project dir to avoid use such a long PATH.


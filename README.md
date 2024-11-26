# Latest source of official WCH OpenOCD (2024-11-26 version)

This repo is the latest source of WCH OpenOCD **(2024-11-26 version)**.

- work with all version of WCH-Link / LinkE / LinkS / LinkW debuggers.
- support program / debug all WCH ch32v/x/l series MCUs and some MCU models in future.

**Please make sure your WCH-Link/E already update to the latest firmware to void possible error when programming. If you do not want to update WCH-LinkE, you can stay with [old version WCH OpenOCD](https://github.com/cjacker/wch-openocd-2022).**

## Update WCH-LinkE firmware

There is two way to update WCH-LinkE firmware:

1. If you have windows:
Download [WCH-LinkUtility](https://www.wch.cn/downloads/WCH-LinkUtility_ZIP.html) and use it update WCH-LinkE firmware. when you connect to target, it will popup a window to ask you update firmware or not.

3. If you have another workable WCH-LinkE:
You can use it to flash the outdated WCH-LinkE, wire up RVSWD pins of two WCH-LinkE and hold the IAP button of target WCH-LinkE down when power on and flash corresponding firmware to outdated WCH-LinkE. for example, the firmware for CH32V305FBP6 is 'WCH-LinkE-APP-IAP.bin' shipped within WCH-LinkUtility.

**I highly DO NOT suggest way 2, since it's very easy to brick a WCH-LinkE if you flash a wrong firmware.**



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


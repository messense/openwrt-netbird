# openwrt-wiretrustee

[![GitHub Actions](https://github.com/messense/openwrt-wiretrustee/workflows/CI/badge.svg)](https://github.com/messense/openwrt-wiretrustee/actions?query=workflow%3ACI)

OpenWrt package for [wiretrustee](https://github.com/wiretrustee/wiretrustee)

## Usage

After installing the package, login the peer with setup key:

```bash
wiretrustee login --setup-key <SETUP_KEY>
```

Start the wiretrustee background service then you're good to go:

```bash
/etc/init.d/wiretrustee enable
/etc/init.d/wiretrustee start
```

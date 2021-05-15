# OpenSBI for Fuxi SoC

This is a fork of [OpenSBI](https://github.com/riscv/opensbi) for [Fuxi SoC](https://github.com/wfly1998/Fuxi)

## Usage

Add prefix for cross compiler:

```sh
$ export CROSS_COMPILE=riscv32-unknown-linux-gnu-
```

Then you cam compile opensbi with following command:

```sh
make PLATFORM=fpga/fuxi
```

After compiling, opensbi will be at `./build/platform/fpga/fuxi/firmware/fw_jump.bin`

For using it for Fuxi SoC, you should use `bin2coe.py` in [GeeOS](https://github.com/wfly1998/GeeOS):

```sh
$ python3 PATH_TO_GEEOS/utiks/bin2coe.py PATH_TO_OPENSBI/build/fpga/fuxi/firmware/fw_jump.bin
```

Then copy the `fw_jump.bin.coe` to Fuxi SoC at `Fuxi/soc/soc.srcs/sources_1/new/ocm.coe`, and you cam generate Fuxi SoC with opensbi for FPGA.


# qemu_x86

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta-small-oses-samples/soletta-basic$ make -C ../BUILD zephyr BOARD=qemu_x86 qemu
make: Entering directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/BUILD'
make -C /home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage qemu MAKEFILE_TOPDIR=/home/abraham/zephyr-project/samples/soletta-small-oses-samples/BUILD/ WORKING_TOPDIR=/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic BUILD_DIR=/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage FBP_SOURCES=""
make[1]: Entering directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage'
Using /home/abraham/zephyr-project/boards/qemu_x86/qemu_x86_defconfig as base
Merging /home/abraham/zephyr-project/kernel/configs/nano.config
Merging prj_qemu_x86.conf
make[2]: Entering directory `/home/abraham/zephyr-project'
make[3]: Entering directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir'
  GEN     ./Makefile
#
# configuration written to .config
#
make[3]: Leaving directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir'
make[2]: Leaving directory `/home/abraham/zephyr-project'
make[2]: Entering directory `/home/abraham/zephyr-project'
make[3]: Entering directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir'
  GEN     ./Makefile
scripts/kconfig/conf --silentoldconfig Kconfig
make[3]: Leaving directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir'
make[3]: Entering directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir'
  Using /home/abraham/zephyr-project as source for kernel
  GEN     ./Makefile
  CHK     include/generated/version.h
  CHK     misc/generated/configs.c
  CHK     include/generated/offsets.h
  CC      samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/src/main.o
  LD      samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/src/built-in.o
  LINK    zephyr.lnk
  SIDT    staticIdt.o
  LINK    zephyr.elf
  BIN     zephyr.bin
To exit from QEMU enter: 'CTRL+a, x'
[QEMU] CPU: qemu32
***** CPU exception 6
Current thread ID = 0x00113940
Faulting segment:address = 0x00000008:0x0000004c
eax: 0x0200000f, ebx: 0x00000000, ecx: 0x00000000, edx: 0x04040404
esi: 0x001e5a9c, edi: 0x001e5a9c, ebp: 0ffffffff, esp: 0x01ffffef
eflags: 0x00000006
Fatal fiber error! Aborting fiber.
```

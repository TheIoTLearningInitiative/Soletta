# Zephyr

- [Compiling Soletta™ Framework for Zephyr](https://github.com/solettaproject/soletta/wiki/Compiling-Soletta%E2%84%A2-Framework-for-Zephyr)

```sh
abraham@aarcemor-desk:~/zephyr-project$ ls
arch    drivers  Kbuild          kernel   MAINTAINERS   misc     scripts
boards  ext      Kconfig         lib      Makefile      net      tests
doc     include  Kconfig.zephyr  LICENSE  Makefile.inc  samples  zephyr-env.sh
abraham@aarcemor-desk:~/zephyr-project$ 
```

## Environment Setup

```sh
abraham@aarcemor-desk:~/zephyr-project$ nano zephyr-env.sh 
abraham@aarcemor-desk:~/zephyr-project$ echo $ZEPHYR_BASE
/home/abraham/zephyr-project
abraham@aarcemor-desk:~/zephyr-project$ export ZEPHYR_GCC_VARIANT=zephyr
abraham@aarcemor-desk:~/zephyr-project$ export ZEPHYR_SDK_INSTALL_DIR=/opt/zephyr-sdk
abraham@aarcemor-desk:~/zephyr-project$ export SOLETTA_BASE_DIR=/home/abraham/soletta
abraham@aarcemor-desk:~/zephyr-project$ 
```

```sh
export ZEPHYR_GCC_VARIANT=zephyr
export ZEPHYR_SDK_INSTALL_DIR=/opt/zephyr-sdk
SOLETTA_BASE_DIR=/home/abraham/soletta
```

## Hello Soletta Base Code

```sh
abraham@aarcemor-desk:~/zephyr-project$ ls
arch     ext      Kconfig.zephyr  MAINTAINERS   net      tests
boards   include  kernel          Makefile      samples  zephyr-env.sh
doc      Kbuild   lib             Makefile.inc  scripts
drivers  Kconfig  LICENSE         misc          soletta
abraham@aarcemor-desk:~/zephyr-project$ cd samples/hello_world/microkernel/
abraham@aarcemor-desk:~/zephyr-project/samples/hello_world/microkernel$ make distclean
make[1]: Entering directory `/home/abraham/zephyr-project'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/hello_world/microkernel/outdir'
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/hello_world/microkernel/outdir'
make[1]: Leaving directory `/home/abraham/zephyr-project'
abraham@aarcemor-desk:~/zephyr-project/samples/hello_world/microkernel$ 
```

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/hello_world/microkernel$ cd ../..abraham@aarcemor-desk:~/zephyr-project/samples$ cp -r hello_world/microkernel/ soletta
```

```sh
abraham@aarcemor-desk:~/zephyr-project/samples$ cd soletta/
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ ls
Makefile  outdir  prj.conf  prj.mdef  README.txt  src
```

## Makefile

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ cat Makefile
```

```sh
MDEF_FILE = prj.mdef
KERNEL_TYPE = micro
BOARD ?= qemu_x86
CONF_FILE = prj.conf

include ${ZEPHYR_BASE}/Makefile.inc
```

```sh
abraham@aarcemor-desk:~/zephyr-project$ echo > Makefile
abraham@aarcemor-desk:~/zephyr-project$ nano Makefile
```

```C
check_vars := $(and $(SOLETTA_BASE_DIR),$(ZEPHYR_BASE),$(ZEPHYR_GCC_VARIANT),$(ZEPHYR_SDK_INSTALL_DIR))
vars_missing := $(if $(check_vars),"","yes")

define NL


endef

ifeq ("yes",$(vars_missing))
$(error $(NL)        Missing environment variables.$(NL)        The Zephyr build requires the following variables to be set:$(NL)$(NL)        ZEPHYR_BASE: Should point to the top Zephyr source directories.$(NL)        ZEPHYR_GCC_VARIANT: The toolchain to use to build Zephyr.$(NL)        ZEPHYR_SDK_INSTALL_DIR: The path where the Zephyr SDK is installed.$(NL)        SOLETTA_BASE_DIR: The path to source of Soletta.$(NL))
endif

KERNEL_TYPE ?= micro
BOARD ?= qemu_x86
MDEF_FILE := prj.mdef

ifneq (,$(realpath $(PWD)/prj_$(BOARD).conf))
CONF_FILE := prj_$(BOARD).conf
else
ifneq (,$(realpath $(PWD)/prj.conf))
CONF_FILE := prj.conf
endif
endif

SOLETTA_CONF = $(realpath $(PWD)/sol_$(BOARD).conf)
ifeq (,$(SOLETTA_CONF))
SOLETTA_CONF = $(realpath $(PWD)/sol.conf)
endif

ifneq (,$(wildcard $(SOLETTA_CONF)))
    export SOLETTA_CONF
endif

include $(ZEPHYR_BASE)/Makefile.inc
```

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ make
Using /home/abraham/zephyr-project/boards/qemu_x86/qemu_x86_defconfig as base
Merging /home/abraham/zephyr-project/kernel/configs/micro.config
Merging prj.conf
#
# configuration written to .config
#
make[1]: Entering directory `/home/abraham/zephyr-project'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/soletta/outdir'
  GEN     ./Makefile
scripts/kconfig/conf --silentoldconfig Kconfig
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/soletta/outdir'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/soletta/outdir'
  Using /home/abraham/zephyr-project as source for kernel
  GEN     ./Makefile
  CHK     include/generated/version.h
  UPD     include/generated/version.h
  HOSTCC  scripts/gen_idt/gen_idt.o
  HOSTLD  scripts/gen_idt/gen_idt
  CHK     misc/generated/configs.c
  UPD     misc/generated/configs.c
  CHK     include/generated/offsets.h
  UPD     include/generated/offsets.h
  CHK     misc/generated/sysgen/prj.mdef
  UPD     misc/generated/sysgen/prj.mdef
  LD      lib/libc/minimal/source/stdlib/built-in.o
  CC      lib/libc/minimal/source/stdout/fprintf.o
  CC      lib/libc/minimal/source/stdout/prf.o
  CC      lib/libc/minimal/source/stdout/sprintf.o
  CC      lib/libc/minimal/source/stdout/stdout_console.o
  LD      lib/libc/minimal/source/stdout/built-in.o
  CC      lib/libc/minimal/source/string/string.o
  LD      lib/libc/minimal/source/string/built-in.o
  LD      lib/libc/minimal/source/built-in.o
  LD      lib/libc/minimal/built-in.o
  LD      lib/libc/built-in.o
  LD      lib/built-in.o
  CC      kernel/microkernel/k_task.o
  CC      kernel/microkernel/k_idle.o
  CC      kernel/microkernel/k_init.o
  CC      kernel/microkernel/k_command_packet.o
  CC      kernel/microkernel/k_move_data.o
  CC      kernel/microkernel/k_ticker.o
  CC      kernel/microkernel/k_memory_map.o
  CC      kernel/microkernel/k_memory_pool.o
  CC      kernel/microkernel/k_irq.o
  CC      kernel/microkernel/k_nop.o
  CC      kernel/microkernel/k_offload.o
  CC      kernel/microkernel/k_event.o
  CC      kernel/microkernel/k_mailbox.o
  CC      kernel/microkernel/k_mutex.o
  CC      kernel/microkernel/k_fifo.o
  CC      kernel/microkernel/k_semaphore.o
  CC      kernel/microkernel/k_timer.o
  CC      kernel/microkernel/k_pipe_buffer.o
  CC      kernel/microkernel/k_pipe.o
  CC      kernel/microkernel/k_pipe_get.o
  CC      kernel/microkernel/k_pipe_put.o
  CC      kernel/microkernel/k_pipe_util.o
  CC      kernel/microkernel/k_pipe_xfer.o
  CC      kernel/microkernel/k_nano.o
  CC      kernel/microkernel/k_server.o
  LD      kernel/microkernel/built-in.o
  CC      kernel/nanokernel/nano_fiber.o
  CC      kernel/nanokernel/nano_lifo.o
  CC      kernel/nanokernel/nano_fifo.o
  CC      kernel/nanokernel/nano_stack.o
  CC      kernel/nanokernel/nano_sys_clock.o
  CC      kernel/nanokernel/nano_context.o
  CC      kernel/nanokernel/nano_init.o
  CC      kernel/nanokernel/nano_sema.o
  CC      kernel/nanokernel/version.o
  CC      kernel/nanokernel/device.o
  CC      kernel/nanokernel/errno.o
  LD      kernel/nanokernel/built-in.o
  LD      kernel/built-in.o
  CC      misc/printk.o
  LD      misc/debug/built-in.o
  CC      misc/generated/configs.o
  CC      misc/generated/sysgen/kernel_main.o
  LD      misc/generated/sysgen/built-in.o
  LD      misc/generated/built-in.o
  LD      misc/built-in.o
  LD      net/built-in.o
  CC      boards/qemu_x86/board.o
  LD      boards/qemu_x86/built-in.o
  LD      boards/built-in.o
  AS      arch/x86/core/i386_sysV_abi/intstub.o
  AS      arch/x86/core/i386_sysV_abi/swap.o
  CC      arch/x86/core/i386_sysV_abi/thread.o
  LD      arch/x86/core/i386_sysV_abi/built-in.o
  CC      arch/x86/core/fatal.o
  CC      arch/x86/core/cpuhalt.o
  CC      arch/x86/core/msr.o
  CC      arch/x86/core/dynamic.o
  CC      arch/x86/core/intconnect.o
  CC      arch/x86/core/excconnect.o
  CC      arch/x86/core/sys_fatal_error_handler.o
  AS      arch/x86/core/crt0.o
  CC      arch/x86/core/atomic.o
  AS      arch/x86/core/cache_s.o
  CC      arch/x86/core/cache.o
  AS      arch/x86/core/excstub.o
  CC      arch/x86/core/strtask.o
  LD      arch/x86/core/built-in.o
  CC      arch/x86/soc/ia32/soc.o
  LD      arch/x86/soc/ia32/built-in.o
  LD      arch/x86/built-in.o
  LD      arch/built-in.o
  LD      ext/hal/built-in.o
  LD      ext/lib/crypto/built-in.o
  LD      ext/lib/built-in.o
  LD      ext/built-in.o
  CC      drivers/console/uart_console.o
  LD      drivers/console/built-in.o
  CC      drivers/interrupt_controller/i8259.o
  CC      drivers/interrupt_controller/system_apic.o
  CC      drivers/interrupt_controller/loapic_intr.o
  CC      drivers/interrupt_controller/ioapic_intr.o
  LD      drivers/interrupt_controller/built-in.o
  LD      drivers/random/built-in.o
  CC      drivers/serial/uart_ns16550.o
  LD      drivers/serial/built-in.o
  CC      drivers/timer/hpet.o
  CC      drivers/timer/sys_clock_init.o
  LD      drivers/timer/built-in.o
  LD      drivers/built-in.o
  CC      samples/soletta/src/main.o
  LD      samples/soletta/src/built-in.o
  LINK    zephyr.lnk
  SIDT    staticIdt.o
  LINK    zephyr.elf
  BIN     zephyr.bin
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/soletta/outdir'
make[1]: Leaving directory `/home/abraham/zephyr-project'
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ 
```

## prj.conf

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ cat prj.conf 
CONFIG_STDOUT_CONSOLE=y
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ 
```

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ nano prj.conf
```

```sh
CONFIG_STDOUT_CONSOLE=y
CONFIG_NEWLIB_LIBC=y
CONFIG_MAIN_STACK_SIZE=256
```

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ make BOARD=qemu_x86
Using /home/abraham/zephyr-project/boards/qemu_x86/qemu_x86_defconfig as base
Merging /home/abraham/zephyr-project/kernel/configs/micro.config
Merging prj.conf
#
# configuration written to .config
#
make[1]: Entering directory `/home/abraham/zephyr-project'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/soletta/outdir'
  GEN     ./Makefile
scripts/kconfig/conf --silentoldconfig Kconfig
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/soletta/outdir'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/soletta/outdir'
  Using /home/abraham/zephyr-project as source for kernel
  GEN     ./Makefile
  CHK     include/generated/version.h
  CHK     misc/generated/configs.c
  UPD     misc/generated/configs.c
  CHK     include/generated/offsets.h
  CHK     misc/generated/sysgen/prj.mdef
  CC      kernel/nanokernel/nano_init.o
  LD      kernel/nanokernel/built-in.o
  LD      kernel/built-in.o
  CC      misc/generated/configs.o
  CC      misc/generated/sysgen/kernel_main.o
  LD      misc/generated/sysgen/built-in.o
  LD      misc/generated/built-in.o
  LD      misc/built-in.o
  LINK    zephyr.lnk
  SIDT    staticIdt.o
  LINK    zephyr.elf
  BIN     zephyr.bin
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/soletta/outdir'
make[1]: Leaving directory `/home/abraham/zephyr-project'
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ 
```

## Makefile.app

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ nano Makefile.app
```

## Makefile.soletta

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ nano Makefile.soletta
```

## sol.conf

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ nano sol.conf
```

## Application

```
abraham@aarcemor-desk:~/soletta/src/samples$ ls
bluetooth  common  design_patterns  http     mqtt     nodejs
coap       crypto  flow             mavlink  network
abraham@aarcemor-desk:~/soletta/src/samples$ cd mqtt/
abraham@aarcemor-desk:~/soletta/src/samples/mqtt$ ls
Kconfig  Makefile  mqtt-publish.c  mqtt-subscribe.c
abraham@aarcemor-desk:~/soletta/src/samples/mqtt$ cp * ~/zephyr-project/samples/soletta/src/
abraham@aarcemor-desk:~/soletta/src/samples/mqtt$ 
```

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta/src$ ls
Kconfig  Makefile  mqtt-publish.c  mqtt-subscribe.c
abraham@aarcemor-desk:~/zephyr-project/samples/soletta/src$ 
```

## Errors

### #error "<dirent.h> not supported"

make distclean your Zephyr Base Code

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ make
make[1]: Entering directory `/home/abraham/zephyr-project'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/soletta/outdir'
  Using /home/abraham/zephyr-project as source for kernel
  GEN     ./Makefile
  CHK     include/generated/version.h
make -C /home/abraham/soletta CFLAGS="-c -g -std=c99 -fno-asynchronous-unwind-tables -Wall -Wno-format-zero-length -Wno-main -ffreestanding -Os -fno-stack-protector -fno-omit-frame-pointer  -ffunction-sections -fdata-sections -mpreferred-stack-boundary=2 -mno-sse -march=lakemont -mtune=lakemont -msoft-float -miamcu  -Wno-unused-but-set-variable -fno-reorder-functions -fno-defer-pop -Wno-pointer-sign -fno-strict-overflow -Werror=implicit-int  -DKERNEL  -I/home/abraham/zephyr-project/arch/x86/include -I/home/abraham/zephyr-project/arch/x86/soc/quark_se -I/home/abraham/zephyr-project/boards/arduino_101  -I/home/abraham/zephyr-project/include -I/home/abraham/zephyr-project/include -I/home/abraham/zephyr-project/samples/soletta/outdir/include/generated -I/home/abraham/zephyr-project/samples/soletta/outdir/misc/generated/sysgen -include /home/abraham/zephyr-project/samples/soletta/outdir/include/generated/autoconf.h  -I/home/abraham/soletta/build/soletta_sysroot/usr/include/soletta -I/opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/include -Wno-missing-include-dirs" LDFLAGS="-nostartfiles -nodefaultlibs -nostdlib -static -L /opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/lib/i586-poky-elfiamcu/5.2.1 -L /opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/lib/" alldefconfig
make[4]: Entering directory `/home/abraham/soletta'
tools/kconfig/conf  --alldefconfig Kconfig
#
# configuration written to .config
#
make[4]: Leaving directory `/home/abraham/soletta'
(cd /home/abraham/soletta; tools/kconfig/merge_config.sh .config /home/abraham/zephyr-project/samples/soletta/sol.conf)
Using .config as base
Merging /home/abraham/zephyr-project/samples/soletta/sol.conf
make[4]: Entering directory `/home/abraham/soletta'
tools/kconfig/conf  --alldefconfig Kconfig
./.tmp.config.gxjkREoh8c:417:warning: override: reassigning to symbol FLOW_NODE_TYPE_GROVE
./.tmp.config.gxjkREoh8c:418:warning: override: reassigning to symbol FLOW_NODE_TYPE_GYROSCOPE
./.tmp.config.gxjkREoh8c:419:warning: override: reassigning to symbol FLOW_NODE_TYPE_JSON
./.tmp.config.gxjkREoh8c:420:warning: override: reassigning to symbol FLOW_NODE_TYPE_LED_7SEG
./.tmp.config.gxjkREoh8c:421:warning: override: reassigning to symbol FLOW_NODE_TYPE_LED_STRIP
./.tmp.config.gxjkREoh8c:422:warning: override: reassigning to symbol FLOW_NODE_TYPE_MAGNETOMETER
#
# configuration written to .config
#
make[4]: Leaving directory `/home/abraham/soletta'
make -C /home/abraham/soletta CFLAGS="-c -g -std=c99 -fno-asynchronous-unwind-tables -Wall -Wno-format-zero-length -Wno-main -ffreestanding -Os -fno-stack-protector -fno-omit-frame-pointer  -ffunction-sections -fdata-sections -mpreferred-stack-boundary=2 -mno-sse -march=lakemont -mtune=lakemont -msoft-float -miamcu  -Wno-unused-but-set-variable -fno-reorder-functions -fno-defer-pop -Wno-pointer-sign -fno-strict-overflow -Werror=implicit-int  -DKERNEL  -I/home/abraham/zephyr-project/arch/x86/include -I/home/abraham/zephyr-project/arch/x86/soc/quark_se -I/home/abraham/zephyr-project/boards/arduino_101  -I/home/abraham/zephyr-project/include -I/home/abraham/zephyr-project/include -I/home/abraham/zephyr-project/samples/soletta/outdir/include/generated -I/home/abraham/zephyr-project/samples/soletta/outdir/misc/generated/sysgen -include /home/abraham/zephyr-project/samples/soletta/outdir/include/generated/autoconf.h  -I/home/abraham/soletta/build/soletta_sysroot/usr/include/soletta -I/opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/include -Wno-missing-include-dirs" LDFLAGS="-nostartfiles -nodefaultlibs -nostdlib -static -L /opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/lib/i586-poky-elfiamcu/5.2.1 -L /opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/lib/"
make[4]: Entering directory `/home/abraham/soletta'
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow-buildopts.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-common-buildopts.h
     GEN   build/stage/lib/common/sol-platform-linux-micro-builtins-gen.h
     GEN   build/stage/lib/common/sol-pin-mux-builtins-gen.h
     GEN   build/stage/lib/common/sol-update-builtins-gen.h
     GEN   build/stage/lib/flow/sol-flow-builtins-gen.h
     GEN   build/stage/lib/flow/sol-flow-metatype-builtins-gen.h
     GEN   include/generated/sol_config.h
In file included from /opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/include/dirent.h:6:0,
                 from ./build/soletta_sysroot/usr/include/soletta/sol-util-file.h:24,
                 from ./src/lib/common/sol-util-internal.h:38,
                 from ./src/shared/sol-lib-loader.c:27:
/opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/include/sys/dirent.h:10:2: error: #error "<dirent.h> not supported"
 #error "<dirent.h> not supported"
  ^
In file included from /opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/include/dirent.h:6:0,
                 from ./build/soletta_sysroot/usr/include/soletta/sol-util-file.h:24,
                 from ./src/lib/common/sol-util-internal.h:38,
                 from ./src/shared/sol-conffile.c:33:
/opt/zephyr-sdk/sysroots/iamc

u-poky-elfiamcu/usr/i586-default-elfiamcu/include/sys/dirent.h:10:2: error: #error "<dirent.h> not supported"
 #error "<dirent.h> not supported"
  ^
In file included from /opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/include/dirent.h:6:0,
                 from ./build/soletta_sysroot/usr/include/soletta/sol-util-file.h:24,
                 from ./src/lib/common/sol-util-internal.h:38,
                 from ./src/shared/sol-fbp-internal-log.c:25:
```

### fatal error: sysgen.h: No such file or directory

When selecting KERNEL_TYPE ?= micro
Change to nano

```sh
      CC   build/stage/lib/io/sol-memmap-storage.o
      CC   build/stage/lib/io/sol-memmap-storage-impl-zephyr.o
In file included from ./src/lib/io/sol-memmap-storage-impl-zephyr.c:19:0:
/home/abraham/zephyr-project/include/zephyr.h:22:20: fatal error: sysgen.h: No such file or directory
compilation terminated.
make[4]: *** [build/stage/lib/io/sol-memmap-storage-impl-zephyr.o] Error 1
make[4]: Leaving directory `/home/abraham/soletta'
make[3]: *** [all] Error 2
make[2]: *** [/home/abraham/soletta/build/soletta_sysroot/usr/lib/libsoletta.a] Error 2
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/soletta/outdir'
make[1]: *** [sub-make] Error 2
make[1]: Leaving directory `/home/abraham/zephyr-project'
make: *** [all] Error 2
abraham@aarcemor-desk:~/zephyr-project/samples/soletta$ 
```

###

```sh
CC   build/stage/lib/io/sol-memmap-storage.o
      CC   build/stage/lib/io/sol-memmap-storage-impl-zephyr.o
make[4]: *** No rule to make target `ipm/ipm_quark_se.h', needed by `build/stage/lib/io/sol-ipm.o'.  Stop.
make[4]: Leaving directory `/home/abraham/soletta'
make[3]: *** [all] Error 2
make[2]: *** [/home/abraham/soletta/build/soletta_sysroot/usr/lib/libsoletta.a] Error 2
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/soletta/outdir'
make[1]: *** [sub-make] Error 2
make[1]: Leaving directory `/home/abraham/zephyr-project'
make: *** [all] Error 2
```
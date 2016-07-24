# Soletta Small OSes Samples

```sh
abraham@aarcemor-desk:~/zephyr-project$ ls
arch     ext      Kconfig.zephyr  MAINTAINERS   net      tests
boards   include  kernel          Makefile      samples  zephyr-env.sh
doc      Kbuild   lib             Makefile.inc  scripts
drivers  Kconfig  LICENSE         misc          soletta
abraham@aarcemor-desk:~/zephyr-project$ cd samples/
abraham@aarcemor-desk:~/zephyr-project/samples$ git clone https://github.com/solettaproject/soletta-small-oses-samples.git
Cloning into 'soletta-small-oses-samples'...
remote: Counting objects: 394, done.
remote: Total 394 (delta 0), reused 0 (delta 0), pack-reused 394
Receiving objects: 100% (394/394), 79.22 KiB | 0 bytes/s, done.
Resolving deltas: 100% (154/154), done.
Checking connectivity... done.
abraham@aarcemor-desk:~/zephyr-project/samples$ 
```

```sh
abraham@aarcemor-desk:~/zephyr-project/samples$ cd soletta-small-oses-samples/
abraham@aarcemor-desk:~/zephyr-project/samples/soletta-small-oses-samples$ ls
BUILD                ipm-flow-adc  oic-server           soletta-coap-server
contiki-coap-server  LICENSE       README.md            soletta-flow
COPYING              lwm2m-client  RIOT                 soletta-memmap
ipm                  lwm2m-server  soletta-basic
ipm-flow             oic-client    soletta-coap-client
abraham@aarcemor-desk:~/zephyr-project/samples/soletta-small-oses-samples$ 
```

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta-small-oses-samples/soletta-basic$ ls
config.riot  config.zephyr  Makefile.application  src
abraham@aarcemor-desk:~/zephyr-project/samples/soletta-small-oses-samples/soletta-basic$ 
```

```sh
abraham@aarcemor-desk:~/zephyr-project/samples/soletta-small-oses-samples/soletta-basic$ make -C ../BUILD zephyr BOARD=quark_se_devboard flash
make: Entering directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/BUILD'
make -C /home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage flash MAKEFILE_TOPDIR=/home/abraham/zephyr-project/samples/soletta-small-oses-samples/BUILD/ WORKING_TOPDIR=/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic BUILD_DIR=/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage FBP_SOURCES=""
make[1]: Entering directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage'
Using /home/abraham/zephyr-project/boards/quark_se_devboard/quark_se_devboard_defconfig as base
Merging /home/abraham/zephyr-project/kernel/configs/nano.config
Merging prj.conf
make[2]: Entering directory `/home/abraham/zephyr-project'
make[3]: Entering directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir'
  HOSTCC  scripts/basic/fixdep
  HOSTCC  scripts/gen_idt/version.o
  HOSTCC  scripts/gen_idt/gen_idt.o
  HOSTLD  scripts/gen_idt/gen_idt
  HOSTCC  scripts/gen_offset_header/gen_offset_header.o
  HOSTLD  scripts/gen_offset_header/gen_offset_header
  GEN     ./Makefile
  HOSTCC  scripts/kconfig/conf.o
  SHIPPED scripts/kconfig/zconf.tab.c
  SHIPPED scripts/kconfig/zconf.lex.c
  SHIPPED scripts/kconfig/zconf.hash.c
  HOSTCC  scripts/kconfig/zconf.tab.o
  HOSTLD  scripts/kconfig/conf
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
  UPD     include/generated/version.h
make -C /home/abraham/soletta CFLAGS="-c -g -std=c99 -fno-asynchronous-unwind-tables -Wall -Wno-format-zero-length -Wno-main -ffreestanding -Os -fno-stack-protector -fno-omit-frame-pointer  -ffunction-sections -fdata-sections -mpreferred-stack-boundary=2 -mno-sse -march=lakemont -mtune=lakemont -msoft-float -miamcu  -Wno-unused-but-set-variable -fno-reorder-functions -fno-defer-pop -Wno-pointer-sign -fno-strict-overflow -Werror=implicit-int  -DKERNEL  -I/home/abraham/zephyr-project/arch/x86/include -I/home/abraham/zephyr-project/arch/x86/soc/quark_se -I/home/abraham/zephyr-project/boards/quark_se_devboard  -I/home/abraham/zephyr-project/include -I/home/abraham/zephyr-project/include -I/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir/include/generated -I/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir/misc/generated/sysgen -include /home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir/include/generated/autoconf.h  -I/home/abraham/soletta/build/soletta_sysroot/usr/include/soletta  -I/home/abraham/zephyr-project/drivers -I/opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/include -Wno-missing-include-dirs " LDFLAGS="-nostartfiles -nodefaultlibs -nostdlib -static -L /opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/lib/i586-poky-elfiamcu/5.2.1 -L /opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/lib/" alldefconfig
make[5]: Entering directory `/home/abraham/soletta'
tools/kconfig/conf  --alldefconfig Kconfig
#
# configuration written to .config
#
make[5]: Leaving directory `/home/abraham/soletta'
(cd /home/abraham/soletta; tools/kconfig/merge_config.sh .config /home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/sol.conf)
Using .config as base
Merging /home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/sol.conf
make[5]: Entering directory `/home/abraham/soletta'
tools/kconfig/conf  --alldefconfig Kconfig
./.tmp.config.gs7KTgVlZR:244:warning: override: reassigning to symbol NETWORK
./.tmp.config.gs7KTgVlZR:245:warning: override: reassigning to symbol USE_IPM
./.tmp.config.gs7KTgVlZR:246:warning: override: reassigning to symbol USE_MEMMAP
#
# configuration written to .config
#
make[5]: Leaving directory `/home/abraham/soletta'
make -C /home/abraham/soletta CFLAGS="-c -g -std=c99 -fno-asynchronous-unwind-tables -Wall -Wno-format-zero-length -Wno-main -ffreestanding -Os -fno-stack-protector -fno-omit-frame-pointer  -ffunction-sections -fdata-sections -mpreferred-stack-boundary=2 -mno-sse -march=lakemont -mtune=lakemont -msoft-float -miamcu  -Wno-unused-but-set-variable -fno-reorder-functions -fno-defer-pop -Wno-pointer-sign -fno-strict-overflow -Werror=implicit-int  -DKERNEL  -I/home/abraham/zephyr-project/arch/x86/include -I/home/abraham/zephyr-project/arch/x86/soc/quark_se -I/home/abraham/zephyr-project/boards/quark_se_devboard  -I/home/abraham/zephyr-project/include -I/home/abraham/zephyr-project/include -I/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir/include/generated -I/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir/misc/generated/sysgen -include /home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir/include/generated/autoconf.h  -I/home/abraham/soletta/build/soletta_sysroot/usr/include/soletta  -I/home/abraham/zephyr-project/drivers -I/opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/include -Wno-missing-include-dirs " LDFLAGS="-nostartfiles -nodefaultlibs -nostdlib -static -L /opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/lib/i586-poky-elfiamcu/5.2.1 -L /opt/zephyr-sdk/sysroots/iamcu-poky-elfiamcu/usr/i586-default-elfiamcu/lib/"
make[5]: Entering directory `/home/abraham/soletta'
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow-buildopts.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-common-buildopts.h
     GEN   build/stage/lib/common/sol-update-builtins-gen.h
     GEN   build/stage/lib/flow/sol-flow-builtins-gen.h
     GEN   build/stage/lib/flow/sol-flow-metatype-builtins-gen.h
     GEN   include/generated/sol_config.h
     GEN   build/soletta_sysroot/usr/bin/sol-flow-node-type-gen.py
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/app.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/timer.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/update.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/constant.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/calamari.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/gpio.h
      CC   build/stage/modules/flow/gpio/gpio.o
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/pwm.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/platform.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/power-supply.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/console.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/color.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/switcher.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/piezo-speaker.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/int.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/form.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/timestamp.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/converter.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/led-strip.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/json.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/jhd1313m1.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/filter-repeated.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/trigonometry.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/boolean.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/wallclock.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/random.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/test.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/am2315.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/float.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/servo-motor.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/string.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/temperature.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/led-7seg.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/format.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/grove.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/aio.h
      CC   build/stage/modules/flow/aio/aio.o
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/compass.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/byte.h
make[5]: Leaving directory `/home/abraham/soletta'
make[5]: Entering directory `/home/abraham/soletta'
     GEN   build/soletta_sysroot/usr/bin/sol-flow-node-type-aliases-gen.py
     GEN   ./build/soletta_sysroot/usr/share//soletta//flow//aliases//50-default.json
Alias file saved at ./build/soletta_sysroot/usr/share//soletta//flow//aliases//50-default.json
     GEN   build/stage/bin/cpp/headers.cc
     GEN   build/soletta_sysroot/usr/lib//pkgconfig/soletta.pc
      CC   build/stage/modules/flow/byte/byte.o
      CC   build/stage/modules/flow/compass/compass.o
      CC   build/stage/modules/flow/grove/grove.o
      CC   build/stage/modules/flow/format/format.o
      CC   build/stage/modules/flow/format/string-format.o
      CC   build/stage/modules/flow/form/form-common.o
      CC   build/stage/modules/flow/led-7seg/led-7seg.o
      CC   build/stage/modules/flow/temperature/temperature.o
      CC   build/stage/modules/flow/string/string-uuid.o
      CC   build/stage/modules/flow/string/string-common.o
      CC   build/stage/modules/flow/string/string-ascii.o
      CC   build/stage/modules/flow/string/string-replace-ascii.o
      CC   build/stage/modules/flow/servo-motor/servo-motor.o
      CC   build/stage/modules/flow/float/float.o
      CC   build/stage/modules/flow/am2315/am2315.o
      CC   build/stage/modules/flow/am2315/nodes.o
      CC   build/stage/modules/flow/test/blob-validator.o
      CC   build/stage/modules/flow/test/boolean-generator.o
      CC   build/stage/modules/flow/test/boolean-validator.o
      CC   build/stage/modules/flow/test/byte-generator.o
      CC   build/stage/modules/flow/test/byte-validator.o
      CC   build/stage/modules/flow/test/float-generator.o
      CC   build/stage/modules/flow/test/float-validator.o
      CC   build/stage/modules/flow/test/int-generator.o
      CC   build/stage/modules/flow/test/int-validator.o
      CC   build/stage/modules/flow/test/result.o
      CC   build/stage/modules/flow/test/string-generator.o
      CC   build/stage/modules/flow/test/string-validator.o
      CC   build/stage/modules/flow/test/test.o
      CC   build/stage/modules/flow/random/random.o
      CC   build/stage/modules/flow/wallclock/wallclock.o
      CC   build/stage/modules/flow/boolean/boolean.o
      CC   build/stage/modules/flow/trigonometry/trigonometry.o
      CC   build/stage/modules/flow/filter-repeated/filter-repeated.o
      CC   build/stage/modules/flow/jhd1313m1/jhd1313m1.o
      CC   build/stage/modules/flow/json/json.o
      CC   build/stage/modules/flow/led-strip/lpd8806.o
      CC   build/stage/modules/flow/converter/converter.o
      CC   build/stage/modules/flow/timestamp/timestamp.o
      CC   build/stage/modules/flow/form/form.o
      CC   build/stage/modules/flow/int/int.o
      CC   build/stage/modules/flow/piezo-speaker/piezo-speaker.o
      CC   build/stage/modules/flow/switcher/switcher.o
      CC   build/stage/modules/flow/color/color.o
      CC   build/stage/modules/flow/console/console.o
      CC   build/stage/modules/flow/power-supply/power-supply.o
      CC   build/stage/modules/flow/platform/platform.o
      CC   build/stage/modules/flow/pwm/pwm.o
      CC   build/stage/modules/flow/calamari/calamari.o
      CC   build/stage/modules/flow/constant/constant.o
      CC   build/stage/modules/flow/update/update.o
      CC   build/stage/modules/flow/timer/timer.o
      CC   build/stage/modules/flow/app/app.o
      CC   build/stage/lib/flow/sol-flow-node-options.o
      CC   build/stage/lib/flow/sol-flow-packet.o
      CC   build/stage/lib/flow/sol-flow-simple-c-type.o
      CC   build/stage/lib/flow/sol-flow-single.o
      CC   build/stage/lib/flow/sol-flow-static.o
      CC   build/stage/lib/flow/sol-flow.o
      CC   build/stage/lib/parsers/sol-json.o
      CC   build/stage/lib/common/sol-blob.o
      CC   build/stage/lib/common/sol-mainloop.o
      CC   build/stage/lib/common/sol-platform.o
      CC   build/stage/lib/common/sol-types.o
      CC   build/stage/lib/common/sol-util.o
      CC   build/stage/lib/common/sol-mainloop-common.o
      CC   build/stage/lib/common/sol-mainloop-impl-zephyr.o
      CC   build/stage/lib/common/sol-platform-impl-zephyr.o
      CC   build/stage/lib/common/sol-util-impl-zephyr.o
      CC   build/stage/lib/common/sol-update.o
      CC   build/stage/lib/common/sol-log.o
      CC   build/stage/lib/common/sol-log-impl-zephyr.o
      CC   build/stage/lib/crypto/sol-crypto.o
      CC   build/stage/lib/io/sol-aio-common.o
      CC   build/stage/lib/io/sol-aio-impl-zephyr.o
      CC   build/stage/lib/io/sol-gpio-common.o
      CC   build/stage/lib/io/sol-gpio-impl-zephyr.o
      CC   build/stage/lib/io/sol-pwm-common.o
      CC   build/stage/lib/io/sol-pwm-impl-zephyr.o
      CC   build/stage/lib/io/sol-i2c-common.o
      CC   build/stage/lib/io/sol-i2c-impl-zephyr.o
      CC   build/stage/lib/io/sol-spi-common.o
      CC   build/stage/lib/io/sol-spi-impl-zephyr.o
      CC   build/stage/lib/datatypes/sol-arena.o
      CC   build/stage/lib/datatypes/sol-buffer.o
      CC   build/stage/lib/datatypes/sol-memdesc.o
      CC   build/stage/lib/datatypes/sol-str-slice.o
      CC   build/stage/lib/datatypes/sol-str-table.o
      CC   build/stage/lib/datatypes/sol-vector.o
      CC   build/stage/shared/sol-modules.o
      CC   build/stage/shared/sol-monitors.o
      CC   build/stage/shared/sol-random.o
      CC   build/stage/shared/sol-fbp-graph.o
      CC   build/stage/shared/sol-fbp-internal-scanner.o
      CC   build/stage/shared/sol-fbp-parser.o
      CC   build/stage/shared/sol-fbp-internal-log.o
      AR   build/stage/shared/libsolettashared.a
      AR   build/soletta_sysroot/usr/lib/libsoletta.a
    INST   ./data/schemas/node-type-genspec.schema
    INST   ./data/jsons/50-default.json
    INST   ./data/gdb/libsoletta.so-gdb.py
*** ATTENTION:
     [!]   You're building the string nodes module without i18n support. That way, some nodes will only act properly on pure ASCII input, not the intended UTF-8 for Soletta. Please re-configure after you have ICU development packages installed to get the intended string nodes behavior.
make[5]: Leaving directory `/home/abraham/soletta'
  HOSTCC  scripts/gen_idt/gen_idt.o
  HOSTLD  scripts/gen_idt/gen_idt
  CHK     misc/generated/configs.c
  UPD     misc/generated/configs.c
  CHK     include/generated/offsets.h
  UPD     include/generated/offsets.h
  CC      lib/libc/newlib/libc-hooks.o
  LD      lib/libc/newlib/built-in.o
  LD      lib/libc/built-in.o
  LD      lib/built-in.o
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
  CC      kernel/nanokernel/nano_sleep.o
  CC      kernel/nanokernel/nano_timer.o
  CC      kernel/nanokernel/ring_buffer.o
  CC      kernel/nanokernel/errno.o
  LD      kernel/nanokernel/built-in.o
  LD      kernel/built-in.o
  CC      misc/printk.o
  LD      misc/debug/built-in.o
  CC      misc/generated/configs.o
  LD      misc/generated/built-in.o
  LD      misc/built-in.o
  LD      net/built-in.o
  CC      boards/quark_se_devboard/pinmux.o
  CC      boards/quark_se_devboard/board.o
  LD      boards/quark_se_devboard/built-in.o
  LD      boards/built-in.o
  CC      arch/x86/core/iamcu_abi/swap.o
  CC      arch/x86/core/iamcu_abi/intstub.o
  CC      arch/x86/core/iamcu_abi/thread.o
  AS      arch/x86/core/iamcu_abi/iamcu.o
  LD      arch/x86/core/iamcu_abi/built-in.o
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
  LD      arch/x86/core/built-in.o
  CC      arch/x86/soc/quark_se/soc.o
  CC      arch/x86/soc/quark_se/soc_config.o
  CC      arch/x86/soc/quark_se/eoi.o
  LD      arch/x86/soc/quark_se/built-in.o
  LD      arch/x86/built-in.o
  LD      arch/built-in.o
  CC      ext/hal/qmsi/drivers/clk.o
  CC      ext/hal/qmsi/drivers/qm_uart.o
  LD      ext/hal/qmsi/built-in.o
  LD      ext/hal/built-in.o
  LD      ext/lib/crypto/built-in.o
  LD      ext/lib/built-in.o
  LD      ext/built-in.o
  CC      drivers/console/uart_console.o
  CC      drivers/console/ipm_console_receiver.o
  LD      drivers/console/built-in.o
  CC      drivers/interrupt_controller/system_apic.o
  CC      drivers/interrupt_controller/loapic_intr.o
  CC      drivers/interrupt_controller/ioapic_intr.o
  LD      drivers/interrupt_controller/built-in.o
  CC      drivers/ipm/ipm_quark_se.o
  LD      drivers/ipm/built-in.o
  LD      drivers/pinmux/built-in.o
  LD      drivers/random/built-in.o
  CC      drivers/serial/uart_qmsi.o
  LD      drivers/serial/built-in.o
  CC      drivers/timer/loapic_timer.o
  CC      drivers/timer/sys_clock_init.o
  LD      drivers/timer/built-in.o
  LD      drivers/built-in.o
  CC      samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/src/main.o
  LD      samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/src/built-in.o
  LINK    zephyr.lnk
  SIDT    staticIdt.o
  LINK    zephyr.elf
  BIN     zephyr.bin
Flashing quark_se_devboard
Flashing Target Device
Open On-Chip Debugger 0.9.0-dirty (2016-05-11-16:25)
Licensed under GNU GPL v2
For bug reports, read
	http://openocd.org/doc/doxygen/bugs.html
Info : auto-selecting first available session transport "jtag". To override use 'transport select <transport>'.
adapter speed: 1000 kHz
trst_only separate trst_push_pull
jtag_ntrst_delay: 300
Error: no device found
Error: unable to open ftdi device with vid 0403, pid 6010, description '*' and serial '*'

Done flashing
make[3]: Leaving directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage/outdir'
make[2]: Leaving directory `/home/abraham/zephyr-project'
make[1]: Leaving directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/soletta-basic/zephyr_stage'
make: Nothing to be done for `flash'.
make: Leaving directory `/home/abraham/zephyr-project/samples/soletta-small-oses-samples/BUILD'
abraham@aarcemor-desk:~/zephyr-project/samples/soletta-small-oses-samples/soletta-basic$ 
```
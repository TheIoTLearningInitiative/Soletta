# x86

# Download

```sh
abraham@aarcemor-desk:~$ git clone https://github.com/solettaproject/soletta.git
Cloning into 'soletta'...
remote: Counting objectsulding2, done.
remote: Compressing objects: 100% (194/194), done.
remote: Total 33462 (delta 83), reused 3 (delta 3), pack-reused 33261
Receiving objects: 100% (33462/33462), 21.34 MiB | 1.03 MiB/s, done.
Resolving deltas: 100% (25446/25446), done.
Checking connectivity... done.
abraham@aarcemor-desk:~$ 
```

# Building

```sh
abraham@aarcemor-desk:~$ cd soletta/
abraham@aarcemor-desk:~/soletta$ make thirdparty-update
Submodule 'src/thirdparty/duktape' (https://github.com/solettaproject/duktape-release.git) registered for path 'src/thirdparty/duktape'
Submodule 'src/thirdparty/mavlink' (https://github.com/mavlink/c_library.git) registered for path 'src/thirdparty/mavlink'
Submodule 'src/thirdparty/oic-data-models' (https://github.com/OpenInterConnect/IoTDataModels) registered for path 'src/thirdparty/oic-data-models'
Submodule 'src/thirdparty/tinycbor' (https://github.com/01org/tinycbor/) registered for path 'src/thirdparty/tinycbor'
Submodule 'src/thirdparty/tinydtls' (git://git.code.sf.net/p/tinydtls/code) registered for path 'src/thirdparty/tinydtls'
...
Submodule path 'src/thirdparty/duktape': checked out '42c26302ddb44d5341333d2ff928cdbc9621e3f5'
Submodule path 'src/thirdparty/mavlink': checked out '194e833c1fb9221ca3f20f85009e5693b32de431'
Submodule path 'src/thirdparty/oic-data-models': checked out 'd728798857a67a5d3c6f16586a1ddab20cbfa2c4'
Submodule path 'src/thirdparty/tinycbor': checked out '629d5b71823ad91faab60f3f51597f010ad98c0c'
Submodule path 'src/thirdparty/tinydtls': checked out 'ded031bc0642875daa47946d10e974318a5c95c4'
```

```sh
abraham@aarcemor-desk:~/soletta$ make alldefconfig
  HOSTCC tools/kconfig/conf.o
 GEN tools/kconfig/zconf.tab.c
 GEN tools/kconfig/zconf.lex.c
 GEN tools/kconfig/zconf.hash.c
  HOSTCC tools/kconfig/zconf.tab.o
  HOSTCC tools/kconfig/conf
tools/kconfig/conf  --alldefconfig Kconfig
#
# configuration written to .config
#
abraham@aarcemor-desk:~/soletta$ 
```

```sh
abraham@aarcemor-desk:~/soletta$ make -l
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow-buildopts.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-common-buildopts.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-flower-power.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-network.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-socket.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-coap.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-http.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-http-client.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-lwm2m.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-flow.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-flow-inspector.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-flow-metatype.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-flow-packet.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-flow-simple-c-type.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-flow-single.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-flow-static.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-flow-parser.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-flow-resolver.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-flow-builder.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-json.h
    INST   build/soletta_sysroot/usr/include/soletta/soletta.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-atomic.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-log.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-macros.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-mainloop.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-platform.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-power-supply.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-types.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-reentrant.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-util.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-certificate.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-glib-integration.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-pin-mux.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-pin-mux-modules.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-worker-thread.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-update.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-update-modules.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-util-file.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-file-reader.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-platform-linux.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-platform-linux-micro.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-message-digest.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-aio.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-gpio.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-pwm.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-i2c.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-spi.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-uart.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-iio.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-fs-storage.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-efivarfs-storage.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-memmap-storage.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-arena.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-list.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-str-table.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-buffer.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-str-slice.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-memdesc.h
    INST   build/soletta_sysroot/usr/include/soletta/sol-vector.h
     GEN   build/stage/lib/common/sol-platform-linux-micro-builtins-gen.h
     GEN   build/stage/lib/common/sol-pin-mux-builtins-gen.h
     GEN   build/stage/lib/common/sol-update-builtins-gen.h
     GEN   build/stage/lib/flow/sol-flow-builtins-gen.h
     GEN   build/stage/lib/flow/sol-flow-metatype-builtins-gen.h
     GEN   include/generated/sol_config.h
     GEN   build/soletta_sysroot/usr/bin/sol-flow-node-type-gen.py
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/app.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/regexp.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/location.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/flower-power.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/timer.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/file.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/thingspeak.h
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
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/udev.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/form.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/network.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/evdev.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/timestamp.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/http-client.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/converter.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/led-strip.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/json.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/jhd1313m1.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/iio.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/filter-repeated.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/trigonometry.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/boolean.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/keyboard.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/wallclock.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/random.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/test.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/am2315.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/float.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/process.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/servo-motor.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/string.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/temperature.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/led-7seg.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/format.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/grove.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/aio.h
      CC   build/stage/modules/flow/aio/aio.o
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/unix-socket.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/persistence.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/compass.h
     GEN   build/soletta_sysroot/usr/include/soletta/sol-flow/byte.h
     GEN   build/soletta_sysroot/usr/bin/sol-flow-node-type-aliases-gen.py
     GEN   ./build/soletta_sysroot/usr/share//soletta//flow//aliases//50-default.json
Alias file saved at ./build/soletta_sysroot/usr/share//soletta//flow//aliases//50-default.json
     GEN   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/initial-services
     GEN   build/stage/bin/cpp/headers.cc
     GEN   build/soletta_sysroot/usr/lib//pkgconfig/soletta.pc
     GEN   build/stage/samples/flow/c-api/custom-node-types-gen.h
    INST   build/soletta_sysroot/usr/bin/sol-oic-gen.py
    INST   build/soletta_sysroot/usr/bin/sol-flow-node-type-validate.py
      CC   build/stage/modules/flow/byte/byte.o
      CC   build/stage/modules/flow/led-7seg/led-7seg.o
      CC   build/stage/modules/flow/temperature/temperature.o
      CC   build/stage/modules/flow/string/string-uuid.o
      CC   build/stage/modules/flow/string/string-common.o
      CC   build/stage/modules/flow/string/string-icu.o
      CC   build/stage/modules/flow/string/string-replace-icu.o
      CC   build/stage/modules/flow/float/float.o
      CC   build/stage/modules/flow/random/random.o
      CC   build/stage/modules/flow/wallclock/wallclock.o
      CC   build/stage/modules/flow/boolean/boolean.o
      CC   build/stage/modules/flow/trigonometry/trigonometry.o
      CC   build/stage/modules/flow/filter-repeated/filter-repeated.o
      CC   build/stage/modules/flow/converter/converter.o
      CC   build/stage/modules/flow/timestamp/timestamp.o
      CC   build/stage/modules/flow/int/int.o
      CC   build/stage/modules/flow/switcher/switcher.o
      CC   build/stage/modules/flow/color/color.o
      CC   build/stage/modules/flow/console/console.o
      CC   build/stage/modules/flow/platform/platform.o
      CC   build/stage/modules/flow/pwm/pwm.o
      CC   build/stage/modules/flow/constant/constant.o
      CC   build/stage/modules/flow/timer/timer.o
      CC   build/stage/modules/flow/regexp/regexp.o
      CC   build/stage/modules/flow/app/app.o
      CC   build/stage/lib/comms/sol-comms.o
      CC   build/stage/lib/comms/sol-socket.o
      CC   build/stage/lib/comms/sol-network-impl-linux.o
      CC   build/stage/lib/comms/sol-network-util-impl-linux.o
      CC   build/stage/lib/comms/sol-socket-impl-linux.o
      CC   build/stage/lib/comms/coap.o
      CC   build/stage/lib/comms/sol-coap.o
      CC   build/stage/lib/comms/sol-http-common.o
      CC   build/stage/lib/comms/sol-http-client-impl-curl.o
      CC   build/stage/lib/comms/sol-lwm2m.o
./src/lib/comms/sol-lwm2m.c: In function ‘extract_bootstrap_client_info’:
./src/lib/comms/sol-lwm2m.c:743:5: warning: ISO C90 forbids mixed declarations and code [-Wdeclaration-after-statement]
     struct sol_str_slice key, value;
     ^
      CC   build/stage/lib/flow/sol-flow-node-options.o
      CC   build/stage/lib/flow/sol-flow-packet.o
      CC   build/stage/lib/flow/sol-flow-simple-c-type.o
      CC   build/stage/lib/flow/sol-flow-single.o
      CC   build/stage/lib/flow/sol-flow-static.o
      CC   build/stage/lib/flow/sol-flow.o
      CC   build/stage/lib/flow/sol-flow-parser.o
      CC   build/stage/lib/flow/sol-flow-composed.o
      CC   build/stage/lib/flow/sol-flow-resolver.o
      CC   build/stage/lib/flow/sol-flow-builder.o
      CC   build/stage/lib/flow/sol-flow-modules.o
      CC   build/stage/lib/flow/sol-flow-parser-dynamic.o
      CC   build/stage/lib/flow/sol-flow-resolver-conffile.o
      CC   build/stage/lib/parsers/sol-json.o
      CC   build/stage/lib/common/sol-blob.o
      CC   build/stage/lib/common/sol-mainloop.o
      CC   build/stage/lib/common/sol-platform.o
      CC   build/stage/lib/common/sol-types.o
      CC   build/stage/lib/common/sol-util.o
      CC   build/stage/lib/common/sol-mainloop-common.o
      CC   build/stage/lib/common/sol-mainloop-impl-posix.o
      CC   build/stage/lib/common/sol-platform-impl-linux-micro.o
      CC   build/stage/lib/common/sol-platform-linux-common.o
      CC   build/stage/lib/common/sol-file-reader.o
      CC   build/stage/lib/common/sol-util-impl-linux.o
      CC   build/stage/lib/common/sol-board-detect.o
      CC   build/stage/lib/common/sol-pin-mux.o
      CC   build/stage/lib/common/sol-certificate-impl-linux.o
      CC   build/stage/lib/common/sol-update.o
      CC   build/stage/lib/common/sol-util-file.o
      CC   build/stage/lib/common/sol-power-supply-impl-linux.o
      CC   build/stage/lib/common/sol-log.o
      CC   build/stage/lib/common/sol-log-impl-linux.o
      CC   build/stage/lib/common/sol-worker-thread.o
      CC   build/stage/lib/common/sol-worker-thread-impl-posix.o
      CC   build/stage/lib/crypto/sol-crypto.o
      CC   build/stage/lib/crypto/sol-message-digest-common.o
      CC   build/stage/lib/crypto/sol-message-digest-impl-openssl.o
      CC   build/stage/lib/io/sol-aio-common.o
      CC   build/stage/lib/io/sol-aio-impl-linux.o
      CC   build/stage/lib/io/sol-gpio-common.o
      CC   build/stage/lib/io/sol-gpio-impl-linux.o
      CC   build/stage/lib/io/sol-pwm-common.o
      CC   build/stage/lib/io/sol-pwm-impl-linux.o
      CC   build/stage/lib/io/sol-uart-common.o
      CC   build/stage/lib/io/sol-uart-impl-linux.o
      CC   build/stage/lib/io/sol-i2c-common.o
      CC   build/stage/lib/io/sol-i2c-impl-linux.o
      CC   build/stage/lib/io/sol-spi-common.o
      CC   build/stage/lib/io/sol-spi-impl-linux.o
      CC   build/stage/lib/io/sol-iio.o
      CC   build/stage/lib/io/sol-fs-storage.o
      CC   build/stage/lib/io/sol-efivarfs-storage.o
      CC   build/stage/lib/io/sol-memmap-storage.o
      CC   build/stage/lib/io/sol-memmap-storage-impl-linux.o
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
      CC   build/stage/shared/sol-conffile.o
      CC   build/stage/shared/sol-lib-loader.o
      AR   build/stage/shared/libsolettashared.a
      LD   build/soletta_sysroot/usr/lib/libsoletta.so
     BIN   build/soletta_sysroot/usr/bin/sol-aio
     BIN   build/soletta_sysroot/usr/bin/sol-gpio
     BIN   build/soletta_sysroot/usr/bin/sol-fbp-to-dot
     BIN   build/soletta_sysroot/usr/bin/sol-fbp-generator
     BIN   build/soletta_sysroot/usr/bin/sol-fbp-runner
      CC   build/stage/modules/linux-micro/watchdog/watchdog.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/watchdog.so
      CC   build/stage/modules/linux-micro/dbus/dbus.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/dbus.so
      CC   build/stage/modules/linux-micro/hostname/hostname.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/hostname.so
      CC   build/stage/modules/linux-micro/bluetooth/bluetooth.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/bluetooth.so
      CC   build/stage/modules/linux-micro/rc-d/rc-d.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/rc-d.so
      CC   build/stage/modules/linux-micro/fstab/fstab.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/fstab.so
      CC   build/stage/modules/linux-micro/machine-id/machine-id.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/machine-id.so
      CC   build/stage/modules/linux-micro/locale/locale.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/locale.so
      CC   build/stage/modules/linux-micro/console/console.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/console.so
      CC   build/stage/modules/linux-micro/network-up/network-up.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/network-up.so
      CC   build/stage/modules/linux-micro/automount/automount.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/automount.so
      CC   build/stage/modules/linux-micro/sysctl/sysctl.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/linux-micro/sysctl.so
      CC   build/stage/modules/flow/compass/compass.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/compass.so
      CC   build/stage/modules/flow/persistence/persistence.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/persistence.so
      CC   build/stage/modules/flow/unix-socket/unix-socket.o
      CC   build/stage/modules/flow/unix-socket/unix-socket-impl.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/unix-socket.so
      CC   build/stage/modules/flow/grove/grove.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/grove.so
      CC   build/stage/modules/flow/format/format.o
      CC   build/stage/modules/flow/format/string-format.o
      CC   build/stage/modules/flow/form/form-common.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/format.so
./build/stage/modules/flow/format/string-format.o (symbol from plugin): warning: memset used with constant zero length parameter; this could be due to transposed parameters
      CC   build/stage/modules/flow/servo-motor/servo-motor.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/servo-motor.so
      CC   build/stage/modules/flow/process/output.o
      CC   build/stage/modules/flow/process/process.o
      CC   build/stage/modules/flow/process/stdin.o
      CC   build/stage/modules/flow/process/subprocess.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/process.so
      CC   build/stage/modules/flow/am2315/am2315.o
      CC   build/stage/modules/flow/am2315/nodes.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/am2315.so
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
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/test.so
      CC   build/stage/modules/flow/keyboard/keyboard.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/keyboard.so
      CC   build/stage/modules/flow/iio/nodes.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/iio.so
      CC   build/stage/modules/flow/jhd1313m1/jhd1313m1.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/jhd1313m1.so
      CC   build/stage/modules/flow/json/json.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/json.so
      CC   build/stage/modules/flow/led-strip/lpd8806.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/led-strip.so
./build/stage/modules/flow/led-strip/lpd8806.o (symbol from plugin): warning: memset used with constant zero length parameter; this could be due to transposed parameters
      CC   build/stage/modules/flow/http-client/http-client.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/http-client.so
      CC   build/stage/modules/flow/evdev/evdev.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/evdev.so
      CC   build/stage/modules/flow/network/network.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/network.so
      CC   build/stage/modules/flow/form/form.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/form.so
      CC   build/stage/modules/flow/udev/udev.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/udev.so
      CC   build/stage/modules/flow/piezo-speaker/piezo-speaker.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/piezo-speaker.so
      CC   build/stage/modules/flow/power-supply/power-supply.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/power-supply.so
      CC   build/stage/modules/flow/calamari/calamari.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/calamari.so
      CC   build/stage/modules/flow/update/update.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/update.so
      CC   build/stage/modules/flow/thingspeak/thingspeak.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/thingspeak.so
      CC   build/stage/modules/flow/file/file.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/file.so
      CC   build/stage/modules/flow/flower-power/flower-power.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/flower-power.so
      CC   build/stage/modules/flow/location/location.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow/location.so
      CC   build/stage/modules/flow-metatype/http-composed-client/http-composed-client.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/flow-metatype/http-composed-client.so
      CC   build/stage/modules/update/update-common/http.o
      CC   build/stage/modules/update/update-common/file.o
      CC   build/stage/modules/update/linux-micro-efi/linux-micro-efi-update.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/update/linux-micro-efi-update.so
      CC   build/stage/modules/pin-mux/intel-galileo-rev-d/intel-galileo-rev-d.o
      CC   build/stage/modules/pin-mux/intel-common/intel-common.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/pin-mux/intel-galileo-rev-d.so
      CC   build/stage/modules/pin-mux/intel-galileo-rev-g/intel-galileo-rev-g.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/pin-mux/intel-galileo-rev-g.so
      CC   build/stage/modules/pin-mux/intel-edison-rev-c/intel-edison-rev-c.o
     MOD   build/soletta_sysroot/usr/lib/soletta/modules/pin-mux/intel-edison-rev-c.so
    INST   ./data/schemas/node-type-genspec.schema
    INST   ./data/jsons/50-default.json
    INST   ./data/gdb/libsoletta.so-gdb.py
abraham@aarcemor-desk:~/soletta$ 
```

```sh
abraham@aarcemor-desk:~/soletta$ make samples
./data/scripts/check-samples-dependencies.py --samples_root_dir ./src/samples --samples_dependency_check_skip_list ./data/jsons/samples_dependency_check_skip_list.json
     SMP   build/stage/samples/http/download
     SMP   build/stage/samples/http/client
     SMP   build/stage/samples/design_patterns/stream_sample
     SMP   build/stage/samples/coap/coap-sample-client
     SMP   build/stage/samples/coap/coap-sample-server
     SMP   build/stage/samples/coap/lwm2m-sample-server
     SMP   build/stage/samples/coap/lwm2m-sample-client
     SMP   build/stage/samples/coap/lwm2m-sample-bs-server
     GEN   build/stage/samples/flow/http-json/openweathermap-gen.c
     SMP   build/stage/samples/flow/http-json/openweathermap
     GEN   build/stage/samples/flow/http-json/temboo_weather-gen.c
     SMP   build/stage/samples/flow/http-json/temboo_weather
     GEN   build/stage/samples/flow/http-json/temperature_display-gen.c
     SMP   build/stage/samples/flow/http-json/temperature_display
     GEN   build/stage/samples/flow/http-json/weather_from_location-gen.c
     SMP   build/stage/samples/flow/http-json/weather_from_location
     GEN   build/stage/samples/flow/http-json/yahoo_weather-gen.c
     SMP   build/stage/samples/flow/http-json/yahoo_weather
     GEN   build/stage/samples/flow/misc/random-numbers-gen.c
     SMP   build/stage/samples/flow/misc/random-numbers
     GEN   build/stage/samples/flow/misc/tickets_queue-gen.c
     SMP   build/stage/samples/flow/misc/tickets-queue
     GEN   build/stage/samples/flow/misc/change_hostname-gen.c
     SMP   build/stage/samples/flow/misc/change_hostname
     GEN   build/stage/samples/flow/misc/change_timezone-gen.c
     SMP   build/stage/samples/flow/misc/change_timezone
     GEN   build/stage/samples/flow/misc/change_system_clock-gen.c
     SMP   build/stage/samples/flow/misc/change_system_clock
     GEN   build/stage/samples/flow/misc/change_locale-gen.c
     SMP   build/stage/samples/flow/misc/change_locale
     GEN   build/stage/samples/flow/misc/persistence-gen.c
     SMP   build/stage/samples/flow/misc/persistence
     GEN   build/stage/samples/flow/misc/evdev-gen.c
     SMP   build/stage/samples/flow/misc/evdev
     GEN   build/stage/samples/flow/misc/network-status-gen.c
     SMP   build/stage/samples/flow/misc/net-status
     GEN   build/stage/samples/flow/misc/udev-gen.c
     SMP   build/stage/samples/flow/misc/udev
     GEN   build/stage/samples/flow/minnow-calamari/calamari-7seg-segments-gen.c
     SMP   build/stage/samples/flow/minnow-calamari/calamari-7seg-segments
     GEN   build/stage/samples/flow/minnow-calamari/calamari-7seg-value-gen.c
     SMP   build/stage/samples/flow/minnow-calamari/calamari-7seg-value
     GEN   build/stage/samples/flow/minnow-calamari/calamari-buttons-rgb-led-gen.c
     SMP   build/stage/samples/flow/minnow-calamari/calamari-buttons-rgb-led
     GEN   build/stage/samples/flow/minnow-calamari/calamari-led-gen.c
     SMP   build/stage/samples/flow/minnow-calamari/calamari-led
     GEN   build/stage/samples/flow/minnow-calamari/calamari-lever-gen.c
     SMP   build/stage/samples/flow/minnow-calamari/calamari-lever
     GEN   build/stage/samples/flow/minnow-calamari/calamari-rgb-led-gen.c
     SMP   build/stage/samples/flow/minnow-calamari/calamari-rgb-led
     GEN   build/stage/samples/flow/minnow-calamari/calamari-button-accumulator-persistence-gen.c
     SMP   build/stage/samples/flow/minnow-calamari/calamari-button-accumulator-persistence
     GEN   build/stage/samples/flow/minnow-calamari/calamari-button-accumulator-persistence-efivars-gen.c
     SMP   build/stage/samples/flow/minnow-calamari/calamari-button-accumulator-persistence-efivars
     GEN   build/stage/samples/flow/basics/cmdline-args-gen.c
     SMP   build/stage/samples/flow/basics/cmdline-args
     GEN   build/stage/samples/flow/basics/platform-service-gen.c
     SMP   build/stage/samples/flow/basics/platform-service
     GEN   build/stage/samples/flow/basics/simple-gen.c
     SMP   build/stage/samples/flow/basics/simple-fbp
     GEN   build/stage/samples/flow/basics/subprocess_bc-gen.c
     SMP   build/stage/samples/flow/basics/subprocess-bc
     GEN   build/stage/samples/flow/basics/keyboard-gen.c
     SMP   build/stage/samples/flow/basics/keyboard
     GEN   build/stage/samples/flow/basics/set-target-gen.c
     SMP   build/stage/samples/flow/basics/set-target
     GEN   build/stage/samples/flow/basics/weekday-gen.c
     SMP   build/stage/samples/flow/basics/weekday
     GEN   build/stage/samples/flow/basics/timeblock-gen.c
     SMP   build/stage/samples/flow/basics/timeblock
     GEN   build/stage/samples/flow/am2315/am2315-gen.c
     SMP   build/stage/samples/flow/am2315/am2315
     GEN   build/stage/samples/flow/semaphore-monitor/semaphore-monitor-console-gen.c
     SMP   build/stage/samples/flow/semaphore-monitor/semaphore-monitor-console
     SMP   build/stage/samples/flow/c-api/custom-node-types.o
     SMP   build/stage/samples/flow/c-api/highlevel
     SMP   build/stage/samples/flow/c-api/lowlevel
     SMP   build/stage/samples/flow/c-api/simple-c-type
     SMP   build/stage/samples/flow/c-api/find-type
     SMP   build/stage/samples/flow/c-api/single-node
     GEN   build/stage/samples/flow/iio/gyroscope-gen.c
     SMP   build/stage/samples/flow/iio/iio-gyro
     GEN   build/stage/samples/flow/iio/magnet-gen.c
     SMP   build/stage/samples/flow/iio/iio-magnet
     GEN   build/stage/samples/flow/iio/accelerate-gen.c
     SMP   build/stage/samples/flow/iio/iio-accelerate
     GEN   build/stage/samples/flow/iio/color-gen.c
     SMP   build/stage/samples/flow/iio/iio-color
     GEN   build/stage/samples/flow/iio/humidity-gen.c
     SMP   build/stage/samples/flow/iio/iio-humidity
     GEN   build/stage/samples/flow/iio/light-gen.c
     SMP   build/stage/samples/flow/iio/iio-light
     GEN   build/stage/samples/flow/iio/pressure-gen.c
     SMP   build/stage/samples/flow/iio/iio-pressure
     GEN   build/stage/samples/flow/iio/temperature-gen.c
     SMP   build/stage/samples/flow/iio/iio-temperature
     GEN   build/stage/samples/flow/iio/proximity-gen.c
     SMP   build/stage/samples/flow/iio/iio-proximity
     GEN   build/stage/samples/flow/iio/adc-gen.c
     SMP   build/stage/samples/flow/iio/iio-adc
     GEN   build/stage/samples/flow/led-strip/lpd8806-gen.c
     SMP   build/stage/samples/flow/led-strip/lpd8806
     GEN   build/stage/samples/flow/http-client/http-client-generic-gen.c
     SMP   build/stage/samples/flow/http-client/client-generic
     GEN   build/stage/samples/flow/http-client/http-request-gen.c
     SMP   build/stage/samples/flow/http-client/request
     GEN   build/stage/samples/flow/webservices/flower-power-http-gen.c
     SMP   build/stage/samples/flow/webservices/flower-power-http
     GEN   build/stage/samples/flow/webservices/freegeoip-gen.c
     SMP   build/stage/samples/flow/webservices/freegeoip
     GEN   build/stage/samples/flow/webservices/thingspeak-talkback-identify-gen.c
     SMP   build/stage/samples/flow/webservices/thingspeak-identify
     GEN   build/stage/samples/flow/webservices/thingspeak-talkback-smart-lock-gen.c
     SMP   build/stage/samples/flow/webservices/thingspeak-smart-lock
     GEN   build/stage/samples/flow/webservices/thingspeak-channel-update-gen.c
     SMP   build/stage/samples/flow/webservices/thingspeak-channel-update
     GEN   build/stage/samples/flow/trash-disposer/trash-disposer-gen.c
     SMP   build/stage/samples/flow/trash-disposer/trash-disposer
     GEN   build/stage/samples/flow/grove-kit/lcd/grove-lcd-autoscroll-gen.c
     SMP   build/stage/samples/flow/grove-kit/lcd/grove-lcd-autoscroll
     GEN   build/stage/samples/flow/grove-kit/lcd/grove-lcd-cursor-gen.c
     SMP   build/stage/samples/flow/grove-kit/lcd/grove-lcd-cursor
     GEN   build/stage/samples/flow/grove-kit/lcd/grove-lcd-display-gen.c
     SMP   build/stage/samples/flow/grove-kit/lcd/grove-lcd-display
     GEN   build/stage/samples/flow/grove-kit/lcd/grove-lcd-hello-world-gen.c
     SMP   build/stage/samples/flow/grove-kit/lcd/grove-lcd-hello-world
     GEN   build/stage/samples/flow/grove-kit/lcd/grove-lcd-scroll-gen.c
     SMP   build/stage/samples/flow/grove-kit/lcd/grove-lcd-scroll
     GEN   build/stage/samples/flow/grove-kit/lcd/grove-lcd-set-cursor-gen.c
     SMP   build/stage/samples/flow/grove-kit/lcd/grove-lcd-set-cursor
     GEN   build/stage/samples/flow/grove-kit/lcd/grove-lcd-text-direction-gen.c
     SMP   build/stage/samples/flow/grove-kit/lcd/grove-lcd-text-direction
     GEN   build/stage/samples/flow/grove-kit/lcd/grove-lcd-fade-gen.c
     SMP   build/stage/samples/flow/grove-kit/lcd/grove-lcd-fade
     GEN   build/stage/samples/flow/grove-kit/lcd/grove-lcd-form-gen.c
     SMP   build/stage/samples/flow/grove-kit/lcd/grove-lcd-form
     GEN   build/stage/samples/flow/grove-kit/grove-button-gen.c
     SMP   build/stage/samples/flow/grove-kit/grove-button
     GEN   build/stage/samples/flow/grove-kit/grove-buzzer-gen.c
     SMP   build/stage/samples/flow/grove-kit/grove-buzzer
     GEN   build/stage/samples/flow/grove-kit/grove-led-accumulator-gen.c
     SMP   build/stage/samples/flow/grove-kit/grove-led-accumulator
     GEN   build/stage/samples/flow/grove-kit/grove-relay-gen.c
     SMP   build/stage/samples/flow/grove-kit/grove-relay
     GEN   build/stage/samples/flow/grove-kit/grove-sound-sensor-gen.c
     SMP   build/stage/samples/flow/grove-kit/grove-sound-sensor
     GEN   build/stage/samples/flow/grove-kit/grove-led-wave-generator-gen.c
     SMP   build/stage/samples/flow/grove-kit/grove-led-wave-generator
     GEN   build/stage/samples/flow/grove-kit/grove-light-sensor-gen.c
     SMP   build/stage/samples/flow/grove-kit/grove-light-sensor
     GEN   build/stage/samples/flow/grove-kit/grove-rotary-angle-sensor-gen.c
     SMP   build/stage/samples/flow/grove-kit/grove-rotary-angle-sensor
     GEN   build/stage/samples/flow/grove-kit/grove-thermometer-gen.c
     SMP   build/stage/samples/flow/grove-kit/grove-thermometer
     GEN   build/stage/samples/flow/io/pwm-gen.c
     SMP   build/stage/samples/flow/io/io-pwm
     GEN   build/stage/samples/flow/io/servo-motor-gen.c
     SMP   build/stage/samples/flow/io/io-servo-motor
     SMP   build/stage/samples/network/network-status
     SMP   build/stage/samples/network/echo-server
     SMP   build/stage/samples/network/echo-client
     SMP   build/stage/samples/common/linux-micro-init
     SMP   build/stage/samples/common/platform-simple
     SMP   build/stage/samples/common/uart-sample
     SMP   build/stage/samples/crypto/message-digest
     SMP   build/stage/samples/crypto/sha256sum
     GEN   ./build/soletta_sysroot/usr/share//soletta//flow//aliases//50-default.json
Alias file saved at ./build/soletta_sysroot/usr/share//soletta//flow//aliases//50-default.json
abraham@aarcemor-desk:~/soletta$ 
```

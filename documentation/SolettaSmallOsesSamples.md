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

## Compilation Errors

```sh
  CC      samples/soletta-small-oses-samples/soletta-coap-server/zephyr_stage/src/main.o
  LD      samples/soletta-small-oses-samples/soletta-coap-server/zephyr_stage/src/built-in.o
  LINK    zephyr.lnk
i586-poky-elfiamcu-gcc: error: lib/soletta/lib.a: No such file or directory
i586-poky-elfiamcu-gcc: error: lib/soletta/lib.a: No such file or directory
make[3]: *** [.tmp_zephyr.prebuilt] Error 1
```
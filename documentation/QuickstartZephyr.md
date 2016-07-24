# Zephyr

- [Compiling Soletta™ Framework for Zephyr](https://github.com/solettaproject/soletta/wiki/Compiling-Soletta%E2%84%A2-Framework-for-Zephyr)

```sh
abraham@aarcemor-desk:~/zephyr-project$ ls
arch    drivers  Kbuild          kernel   MAINTAINERS   misc     scripts
boards  ext      Kconfig         lib      Makefile      net      tests
doc     include  Kconfig.zephyr  LICENSE  Makefile.inc  samples  zephyr-env.sh
abraham@aarcemor-desk:~/zephyr-project$ mkdir soletta
abraham@aarcemor-desk:~/zephyr-project$ 
```

```sh
abraham@aarcemor-desk:~/zephyr-project$ nano soletta/Makefile
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


# Sandbox

```sh
abraham@aarcemor-desk:~/zephyr-project$ cd $ZEPHYR_BASE/samples/hello_world/microkernel
abraham@aarcemor-desk:~/zephyr-project/samples/hello_world/microkernel$ make BOARD=qemu_x86
make[1]: Entering directory `/home/abraham/zephyr-project'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/hello_world/microkernel/outdir'
  Using /home/abraham/zephyr-project as source for kernel
  GEN     ./Makefile
  CHK     include/generated/version.h
  CHK     misc/generated/configs.c
  CHK     include/generated/offsets.h
  CHK     misc/generated/sysgen/prj.mdef
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/hello_world/microkernel/outdir'
make[1]: Leaving directory `/home/abraham/zephyr-project'
abraham@aarcemor-desk:~/zephyr-project/samples/hello_world/microkernel$ 
```

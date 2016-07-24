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


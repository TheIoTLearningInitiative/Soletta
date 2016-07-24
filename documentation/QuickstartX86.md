# x86

# Download

```sh
abraham@aarcemor-desk:~$ git clone https://github.com/solettaproject/soletta.git
Cloning into 'soletta'...
remote: Counting objects: 33462, done.
remote: Compressing objects: 100% (194/194), done.
remote: Total 33462 (delta 83), reused 3 (delta 3), pack-reused 33261
Receiving objects: 100% (33462/33462), 21.34 MiB | 1.03 MiB/s, done.
Resolving deltas: 100% (25446/25446), done.
Checking connectivity... done.
abraham@aarcemor-desk:~$ 
```

```sh
abraham@aarcemor-desk:~$ cd soletta/
abraham@aarcemor-desk:~/soletta$ make thirdparty-update
Submodule 'src/thirdparty/duktape' (https://github.com/solettaproject/duktape-release.git) registered for path 'src/thirdparty/duktape'
Submodule 'src/thirdparty/mavlink' (https://github.com/mavlink/c_library.git) registered for path 'src/thirdparty/mavlink'
Submodule 'src/thirdparty/oic-data-models' (https://github.com/OpenInterConnect/IoTDataModels) registered for path 'src/thirdparty/oic-data-models'
Submodule 'src/thirdparty/tinycbor' (https://github.com/01org/tinycbor/) registered for path 'src/thirdparty/tinycbor'
Submodule 'src/thirdparty/tinydtls' (git://git.code.sf.net/p/tinydtls/code) registered for path 'src/thirdparty/tinydtls'
...

```
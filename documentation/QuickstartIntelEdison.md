# Intel Edison

# Download

```sh
root@edison:~# git clone https://github.com/solettaproject/soletta.git
Cloning into 'soletta'...
remote: Counting objects: 33462, done.
remote: Compressing objects: 100% (194/194), done.
remote: Total 33462 (delta 83), reused 3 (delta 3), pack-reused 33261
Receiving objects: 100% (33462/33462), 21.34 MiB | 841.00 KiB/s, done.
Resolving deltas: 100% (25446/25446), done.
Checking connectivity... done.
root@edison:~# 
```

```sh
root@edison:~# cd soletta/
root@edison:~/soletta# make thirdparty-update
find: unrecognized: -not
BusyBox v1.22.1 (2016-06-06 14:50:27 PDT) multi-call binary.

Usage: find [-HL] [PATH]... [OPTIONS] [ACTIONS]

/usr/bin/env: python3: No such file or directory
git: 'submodule' is not a git command. See 'git --help'.
tools/build/Makefile.common:100: recipe for target 'thirdparty-update' failed
make: *** [thirdparty-update] Error 1
root@edison:~/soletta# 
```
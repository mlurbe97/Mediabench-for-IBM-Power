# Mediabench-for-IBM-Power

## Author

* Manel Lurbe Sempere (malursem@inf.upv.es)

## Abstract

How to compile and run mediabench on Power PC IBM platforms.
Our testing platform can differ yours. This are our specifications:
- IBM Power System S812L.
- 10-core IBM Power 8 procesor up to SMT 8 running at 3.69 GHz.
- 1 DIMM of 32 GB DDR4 memory on single-channel at 2133MHz.
- Ubuntu 18.04 with Linux Kernel 4.15.

## Documentation

- [MediaBench: A Tool for Evaluating and Synthesizing Multimedia and Communicatons Systems.](https://www.researchgate.net/publication/221005559_MediaBench_A_Tool_for_Evaluating_and_Synthesizing_Multimedia_and_Communicatons_Systems)

## Requisites

Before compile simplescalar compiler must be installed. For this porpose, a simplescalar autoinstallable version is available on simplescalar folder. This installer can be fount at github [How-to-install-SimpleScalar-on-Ubuntu](https://github.com/sdenel/How-to-install-SimpleScalar-on-Ubuntu) developed by sdenel.

## Compile and run

Each benchmark can be compiled as follows or simply running the script [compile_all](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/compile_all) from this repository.

The [mediabench](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/mediabench) folder contains the original benchmarks from the original source edited with the following rules.

### adpcm

- From the original source, to be compiled on the IBM POWER, line 14 of the Makefile must be commented:

```
# CC = /export/ramoth4/bishop/simplescalar/bin/ssbig-na-sstrix-gcc
```

- To compile simply run:

```
    cd mediabench/adpcm/src/
    make clean
    make all
```

- The executables are on the mediabench/adpcm/bin/ folder:

```
    user@computer:~/mediabench/adpcm/bin$ ls
    rawcaudio  rawdaudio  timing
```

### epic

- From the original source, to be compiled on the IBM POWER, line 33 of the Makefile must be commented:

```
# CC = ../../../bin/ssbig-na-sstrix-gcc
```

- In addition, in lines 47 and 49 of the Makefile, *-lm* option must be uncommented.

- To compile simply run:

```
    cd mediabench/epic/src/
    make clean
    make all
```

- The executables are on the mediabench/epic/bin/ folder:

```
    user@computer:~/mediabench/epic/bin$ ls
    epic  unepic
```

### g721

- From the original source, to be compiled on the IBM POWER, line 9 of the Makefile must be commented:

```
# CC =  ../../../bin/ssbig-na-sstrix-gcc # gcc -mv8 -static
```

- To compile simply run:

```
    cd mediabench/g721/src/
    make clean
    make all
```

- The executables are on the mediabench/g721/bin/ folder:

```
    user@computer:~/mediabench/g721/bin$ ls
    decode  encode
```

### ghostscript

stdio muy viejo para ubuntu 18.04

- From the original source, to be compiled on the IBM POWER, line 175 of the Makefile must be commented:

```
# CC=../../../bin/ssbig-na-sstrix-gcc -static -ansi -I ../../../ssbig-na-sstrix/include #gcc -mv8 -static
```

- In addition, in line 325 of the Makefile, *-mv8* option must be commented.

- To compile simply run:

```
    cd mediabench/ghostscript/src/
    make clean
    make all
```

- The executables are on the mediabench/ghostscript/bin/ folder:

```
    user@computer:~/mediabench/ghostscript/bin$ ls
    elbindebeestaraqui
```

### gsm

- To compile simply run:

```
    cd mediabench/gsm/
    make install
```

- The executables are on the mediabench/gsm/bin/ folder:

```
    user@computer:~/mediabench/gsm/bin$ ls
    tcat  toast  untoast
```

### jpeg

- To compile simply run:

```
    cd mediabench/jpeg/jpeg-6a/
    chmod +x configure
    ./configure
    make clean
    make all
    cp -rf cjpeg djpeg jpegtran rdjpgcom wrjpgcom ../bin/
```

- The executables are on the mediabench/jpeg/bin/ folder:

```
    user@computer:~/mediabench/jpeg/bin$ ls
    cjpeg  djpeg  jpegtran  rdjpgcom  wrjpgcom
```

### mesa

- To compile simply run:

```
    cd mediabench/mesa/
    make clean
    make linux
    cd demos/
    make clean
    make linux
```

- The executables are on the mediabench/mesa/exec/ folder:

```
    user@computer:~/mediabench/mesa/exec$ ls
    '!'   demo   out1   out1.ppm   out2   out2.ppm   out3   out3.ppm   run
```

### mpeg2

- Work in progress...

### pegwit

- Work in progress...

### pgp

- Work in progress...

### rasta

- Work in progress...

## License

Mediabench-for-IBM-Power
Copyright (C) 2021  Manel Lurbe Sempere <malursem@inf.upv.es>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
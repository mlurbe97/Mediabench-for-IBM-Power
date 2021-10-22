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

## Compile and run

Each benchmark can be compiled as follows or simply running the script [compile_all](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/compile_all) from this repository.

The [mediabench](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/mediabench) folder contains the original benchmarks from the original source untouched.

### adpcm

- Work in progress...

### epic

- Work in progress...

### g721

- Work in progress...

### ghostscript

- Work in progress...

### gsm

- Work in progress...

### jpeg

- To compile simply run:

```
    cd mediabench/jpeg/jpeg-6a/
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
    make gcc
    cd demos/
    make clean
    make gcc
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
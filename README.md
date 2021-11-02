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

## Compile and run Mediabench

Each benchmark can be compiled as follows or simply running the script [compile_all](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/compile_all) from this repository. Work in progress.

The [mediabench](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/mediabench) folder contains the original benchmarks from the original source edited with the following rules.

### adpcm

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

## Compile and run Mediabench II

Each benchmark can be compiled as follows or simply running the script [compile_all](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/compile_all) from this repository. Work in progress.

The [mediabench2](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/mediabench2) folder contains the original benchmarks from the original source edited with the following rules.

### cjpeg

- To compile simply run:

```
    cd mediabench2/cjpeg/
    tar -xf jpegsrc.v6b.tar.gz
    cd jpeg-6b/
    make clean
    ./configure
    make
```

### djpeg

- If cjpeg is installed:

```
    cd mediabench2/djpeg/
    ln -s ../cjpeg/jpeg-6b/
```

- If not, to compile simply run:

```
    cd mediabench2/djpeg/
    tar -xf jpegsrc.v6b.tar.gz
    cd jpeg-6b/
    make clean
    ./configure
    make
```

### h263enc

- To compile simply run:

```
    cd mediabench2/h263enc/
    tar -xf tmn-1.7.tar.gz
    cd tmn-1.7/
    make clean
    make all
```

### h263dec

- If h263enc is installed:

```
    cd mediabench2/h263dec/
    ln -s ../h263enc/tmn-1.7/
```

- If not, to compile simply run:

```
    cd mediabench2/h263dec/
    tar -xf tmn-1.7.tar.gz
    cd tmn-1.7/
    make clean
    make all
```

### h264enc

- To compile simply run:

```
    cd mediabench2/h264enc/
    unzip jm10.2.zip
    cd JM/
    sh unixprep.sh
    cd lencod/
    make
```

### h264dec

- To compile simply run:

```
    cd mediabench2/h264dec/
    unzip jm10.2.zip
    cd JM/
    sh unixprep.sh
    cd ldecod/
    make
```

### jpg2000enc

- To compile simply run:

```
    cd mediabench2/jpg2000enc/
    unzip jasper-1.701.0.zip
    cd jasper-1.701.0/
    ./configure --build=powerpc
    make
```

### jpg2000dec

- If jpg2000enc is installed:

```
    cd mediabench2/jpg2000dec/
    ln -s ../jpg2000enc/jasper-1.701.0/
```

- If not, to compile simply run:

```
    cd mediabench2/jpg2000dec/
    unzip jasper-1.701.0.zip
    cd jasper-1.701.0/
    ./configure --build=powerpc
    make
```

### mpeg2enc

- To compile simply run:

```
    cd mediabench2/mpeg2enc/
    tar -xf mpeg2vidcodec_v12.tar.gz
    cd mpeg2/
    make
```

### mpeg2dec

- If mpeg2enc is installed:

```
    cd mediabench2/mpeg2dec/
    ln -s ../mpeg2enc/mpeg2/
```

- If not, to compile simply run:

```
    cd mediabench2/mpeg2dec/
    tar -xf mpeg2vidcodec_v12.tar.gz
    cd mpeg2/
    make
```

### mpeg4enc

- To compile simply run:

```
    sudo apt-get install -y libv4l-dev
    sudo ln -s /usr/include/libv4l1-videodev.h   /usr/include/linux/videodev.h 
    cd mediabench2/mpeg4enc/
    tar -xf ffmpeg.2006_04_24.tgz
    cd ffmpeg/
    ./configure --disable-strip
    make
```

### mpeg4dec

- If mpeg4enc is installed:

```
    cd mediabench2/mpeg4dec/
    ln -s ../mpeg4enc/ffmpeg/
```

- If not, to compile simply run:

```
    sudo apt-get install -y libv4l-dev
    sudo ln -s /usr/include/libv4l1-videodev.h   /usr/include/linux/videodev.h 
    cd mediabench2/mpeg4dec/
    tar -xf ffmpeg.2006_04_24.tgz
    cd ffmpeg/
    ./configure --disable-strip
    make
```

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
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

Each benchmark can be compiled as follows or simply running the script [compile_mediabench](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/compile_mediabench) from this repository.

The [mediabench](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/mediabench) folder contains the original benchmarks from the original source edited to be compatible.

## Compile and run Mediabench II

Each benchmark can be compiled as follows or simply running the script [compile_mediabench2](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/compile_mediabench2) from this repository.

The [mediabench2](https://github.com/mlurbe97/Mediabench-for-IBM-Power/blob/master/mediabench2) folder contains the original benchmarks from the original source edited to be compatible.

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
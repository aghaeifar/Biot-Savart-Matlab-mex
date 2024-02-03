# Magnetic Field Calculator with Biot-Savart Law

[![Lates Release](https://img.shields.io/github/v/release/aghaeifar/bloch_simulator)](https://github.com/aghaeifar/Biot-Savart/releases)


This software computes the magnetic field of a coil with an arbitrary shape using the Biot-Savart law. The coil may consist of one or multiple distinct segments. The program employs the analytical solution suggested in [this source](https://physics.stackexchange.com/questions/662024/) to determine the magnetic field generated by a finite thin wire. Input and output units adhere to the International System of Units (SI), "meter" for spatial positions and "tesla" for magnetic field.

Calculation is parallelized over given spatial points. Parallelization is implemented based on STL algorithms. Using a compiler with **C++17** support is required.

### Python interface:
Simply use cmake to compile program as a shared libary. See python example below.

### MATLAB interface: 
Program can be compiled as mex file without any change. see below.


## Installation:

### Linux dependencies:

```sh
sudo apt-get install g++ cmake git libtbb-dev
```
### Build shared library
Clone Biot-Savart simulator from repository:

```sh
git clone https://github.com/aghaeifar/Biot-Savart.git
```

Build and install Bloch simulator as a shared library:

```sh
$ cd Biot-Savart
$ cmake -B ./build
$ cmake --build ./build --config Release
```

### Build MATLAB mex  
#### Linux
```sh
mex biot_savart.cpp  -lm -ldl -ltbb -R2018a CXXFLAGS="\$CXXFLAGS -std=c++17"
```
#### Windows
```sh
mex biot_savart.cpp  -R2018a COMPFLAGS="$COMPFLAGS /std:c++17""
```

My test environment: Ubuntu 22.04 with g++ 11.4 + Windows 11 with MATLAB R2023a and Microsoft Visual C++ 2022.


## Contributing:

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

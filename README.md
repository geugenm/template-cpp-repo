# Modern C++ Template

## Features
- **Latest C++23 Ready Presets**: Take advantage of the latest C++ features with our up-to-date presets.
- **Code Quality Tools Targets**: Integrated targets for maintaining high code quality.
- **CMake Package Manager (CPM)**: Simplifies dependency management.
- **Flexible Doxygen Configuration**: Easily integrated Doxygen setup for documentation.
- **Easy to Setup CTests**: Simplified testing setup with CTest.
- **Docker Ready**: Pre-configured for seamless Docker integration.
- **Compatibility**: Works with QtCreator, CLion, Visual Studio, and KDevelop.
- **Cross-Platform**: Ready for Linux, Windows, and macOS.
- **CMake-Driven**: All setup is done through CMake, eliminating the need for specific scripts, making CI/CD setup straightforward.

## Installation

1. Clone the repository via `git clone --recurse-submodules <repository URL>`
2. Install the required dependencies:
    - `cmake 3.25.0+`
    - `c++ compiler with cpp 23 support`
    - `ninja`
    - `(optional) cmake/cfg/*.cmake tools`
     
### macOS

#### Install Homebrew (if not already installed)
Open your terminal and run:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### Install CMake
Using Homebrew:
```bash
brew install cmake
```

#### Install C++ Compiler (LLVM)
Using Homebrew:
```bash
brew install llvm
```

#### Install Doxygen
Using Homebrew:
```bash
brew install doxygen
```

---

### Windows

#### Install Chocolatey (if not already installed)
Open Command Prompt as Administrator and run:
```bash
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

#### Install CMake
Using Chocolatey:
```bash
choco install cmake
```

#### Install C++ Compiler (Visual Studio Build Tools)
Using Chocolatey:
```bash
choco install visualstudio2019buildtools
```

#### Install Doxygen
Using Chocolatey:
```bash
choco install doxygen
```

---

## Linux (Ubuntu/Debian)

#### Update Package List
```bash
sudo apt update
```

#### Install CMake
```bash
sudo apt install cmake
```

#### Install C++ Compiler (GCC)
```bash
sudo apt install g++
```

#### Install Doxygen
```bash
sudo apt install doxygen
```

---

## Linux (Fedora)

#### Update Package List
```bash
sudo dnf check-update
```

#### Install CMake
```bash
sudo dnf install cmake
```

#### Install C++ Compiler (GCC)
```bash
sudo dnf install gcc-c++
```

#### Install Doxygen
```bash
sudo dnf install doxygen
```

#### Notes:
- Make sure to check the specific package manager commands for your Linux distribution if you're not using Ubuntu or Fedora.
- For Windows, you may also consider installing the full Visual Studio IDE, which includes a C++ compiler and CMake support.

## Build & Deployment

### Build the project 

```bash
cmake --preset=release .
cd build/release
cmake --build . --config release
```
For more build configurations see [CMakePresets.json](CMakePresets.json)

Also, you can use cmake-gui/cmake-cli app to simplify the proccess locally.

#### Run tests

```bash
cd build/release
ctest --output-on-failure
```

### Uninstall the project

```bash
sudo xargs rm < install_manifest.txt
```

### Docker build on manjaro

```bash
docker build -t my-image -f docker/Dockerfile .
```

## Documentation

All you need is to install doxygen and run these commands:
```bash
cd build/release
cmake --build . --target doxygen
```

To browse the generated by cmake html documentation:
```bash
cd build/release/docs/doxygen/html
python -m http.server 8080
```

## Todo
1. Add android build
2. Add ios build

## Contributing

If you'd like to contribute to this project, feel free to fork the repository and submit a pull request with your
changes.Contributions are always welcome, whether it's an improvement to the existing program or a new program in a
different language.

## License

This project is licensed under the AGPL-3.0 License — see the [LICENSE] file for details.

## Acknowledgments

Thanks to the developers of CMake and CTest for providing the tools necessary to build and test this program. Also,
thanks to the open-source community for providing resources and support for C++ development.

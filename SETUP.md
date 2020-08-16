# Aegis setup
This guide walks you through setting up Aegis in Visual Studio on Windows. 

## Steps
1. Clone aegis
2. Install vcpkg
3. Get openssl and zlib
4. Create a new project
5. Include headers
6. Add boilerplate
7. *Zoom*

## Clone aegis
To clone the aegis repository (download it down to your PC) you'll need either Git or GitHub Desktop

### Using Git

#### Install Git
Get the windows installer [here](https://gitforwindows.org/).
It will install git bash, a secondary console so to say. When running git commands, use this console and not the default windows console.

#### Clone ageis
Start git bash and clone aegis with `git clone --recursive https://github.com/zeroxs/aegis.cpp <destination folder>`.
Replace `<destination folder>` with where you want it to be cloned.
Keep in mind where the repository was cloned, since you'll need to reference it later (when we need to include its headers).

### Using GitHub Desktop

### Install GitHub dekstop
Get the windows installer [here](https://desktop.github.com/) and install

#### Clone ageis
Start GitHub desktop and locate the top menu bar. Then go to `File` -> `Clone repository` -> `URL`.
In the first field add `https://github.com/zeroxs/aegis.cpp` and in the second field where you want it to be cloned.
Keep in mind where the repository was cloned, since you'll need to reference it later (when we need to include its headers).

## Install vcpkg
Follow [this](https://github.com/microsoft/vcpkg#quick-start-windows) guide to install vcpkg.
The important bits are `git clone https://github.com/microsoft/vcpkg`, `vcpkg\bootstrap-vcpkg.bat` and `vcpkg\vcpkg integrate install`.
If you in the previous step used GitHub dekstop, ignore `git clone https://github.com/microsoft/vcpkg` and instead clone it like you cloned ageis.

## Get openssl and zlib
Using our newly created `vcpkg.exe` get the openssl and zlib packages with `vcpkg install openssl` and `vcpkg install zlib`.

## Create a new project
Restart VS and start a new project, to make sure the packages we just got are recognised.

## Include headers
Aegis will try to use headers in multiple different folders inside the aegis folder, so we need to tell VS about those folders.
Open your project in VS and locate the top menu bar. Then go to `Project` -> `Properties` -> `Configuration Properties` -> `C/C++` -> `General` -> `Additional Include Directories`.
In this field you should add the folowing folders
- `aegis.cpp\include`
- `aegis.cpp\lib\websocketpp`
- `aegis.cpp\lib\spdlog\include`
- `aegis.cpp\lib\json\include`
- `aegis.cpp\lib\asio\asio\include`

Replace `aegis.cpp` by the full path to the aegis directory. This is the directory I mentioned earlier that you should keep in mind.

## Add boilerplate
Add the following preprocessor directives on top
```
#define _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS
#define _CRT_SECURE_NO_WARNINGS
#define _SCL_SECURE_NO_WARNINGS
#define _HAS_AUTO_PTR_ETC 1
#include <aegis.hpp>
```

## *Zoom*
That should be it.


<br/><br/><br/><br/><br/><br/>

<sup><sub>Sharon can suck my dick, imagine not providing any guide for setting up your own library.
As if the library wasn't already undocumented enough and sharon wasn't already a huge dick.</sub></sup>

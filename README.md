# Project Template for modm+CMake

This project template is used for quick start of bare metal embedded projects with [modm](https://modm.io/) C++ library.
The template is intended for CMake-based builds which in turn enables use of several IDE's - CLion, Eclipse, KDevelop, QtCreator for development of embedded projects.

## Prerequisites

- [Python 3](https://www.python.org/)
- [Library Builder](https://github.com/modm-io/lbuild)
- [GNU ARM Embedded Toolchain](https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads)
- [OpenOCD](http://openocd.org/)

## Getting Started
Configuration of the new project from this project template is quite simple:
 - Clone repository
 - Configure/update `project.xml`
 - Generate library and build system files
 
### Clone repository
 Following command will properly clone project template into new project: 
 ```
 $ git clone --recurvise https://github.com/siy/modm-cmake-template.git <my-new-project>
``` 
Note that template uses [git submodules](https://blog.github.com/2016-02-01-working-with-submodules/), so it must be cloned recursively.

### Configure/update `project.xml`
The [modm Getting Started](https://modm.io/guide/getting-started/) page contains information about `project.xml` configuration. 
Also, [modm examples](https://github.com/modm-io/modm/tree/develop/examples/) contains several examples of this file. The `project.xml` must be configured to use CMake build system. This is done by adding `CMake` module into `project.xml`:
```
<library>
 ...
  <modules>
 ...
    <module>:build:cmake</module>
 ...
  </modules>
 ...
</library>
```
##  Generate library and build system files
The customized version of the modm and build system files are generated with following command: 
```
$lbuild build
```

Now project can be imported into preferred IDE as either CMake or Makefile project. 

Enjoy!

# License 
This project uses the same license as modm - Mozilla Public License v2.0

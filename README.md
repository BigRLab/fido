FIDO
==

Fido is a minimalistic C/C++ project generator supporting various templates.

Installation
==

    python setup.py build
    sudo python setup.py install

Usage
==

    Usage: fido <action> [template] (path)

    Available actions:

                    help : Print the usage menu.
                  create : Create a project with the specified template, requires a template and a path.
                   build : Build the current project.
                   clean : Clean built files for the current project.

    Available templates:

          android-make-c : Create a native Android C project based on Makefile.
        android-make-cpp : Create a native Android C++ project based on Makefile.
                 cmake-c : Create a C project based on CMake.
               cmake-cpp : Create a C++ project based on CMake.
                  make-c : Create a C project based on Makefile.
                make-cpp : Create a C++ project based on Makefile.

Example
==

    # fido create android-make-cpp android-sample --NDK=/opt/ndk
    
    [-] Creating project 'android-sample' with template 'android-make-cpp' ...
      - Creating project '.fido' file ...
      - Updating variable '#PROJECT_NAME#' in android-sample/Makefile ...
      - Updating variable '#NDK_PATH#' in android-sample/Makefile ...
      - Updating variable '#PROJECT_NAME#' in android-sample/.gitignore ...
      - Updating variable '#PROJECT_NAME#' in android-sample/README.md ...
      - Updating variable '#PROJECT_NAME#' in android-sample/src/main.cpp ...
    [-] DONE

    # cd android-sample
    # ls
    
    include  Makefile  README.md  src

    # fido build
    # file android-sample
    
    android-sample: ELF 32-bit LSB shared object, ARM, EABI5 version 1 (SYSV), dynamically linked (uses shared libs), not stripped

License
==

This project is copyleft of [Simone Margaritelli](http://www.evilsocket.net/) and released under the GPL 3 license.
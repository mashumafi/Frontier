# Frontier

A chess engine written in the experimental [cppfront](https://github.com/hsutter/cppfront).

## About

### CMake

CMake is used to pull in and build cppfront. It manages the dependcies of compiling cpp2 to cpp1 syntax. This all works seamlessly and even breakpoints work. All CMake functions and logic will go into [src/thirdparty/cppfront/CMakeLists.txt](//github.com/mashumafi/frontier/blob/main/src/thirdparty/cppfront/CMakeLists.txt)

### Goals

* Easy to read and learn chess engine
* Use pure cpp2 when possible
* Use modern features
  * pmr (polymorphic memory resources)
  * `#include <bits>`
  * `#include <bitset>`
* Try to be self-contained (low dependencies)

### Project Structure

The project aims to organize and modularize logic to attempt to make browsing and learning easier for new users.

All the source code goes into the [src](//github.com/mashumafi/frontier/blob/main/src) folder. Generally libraries are header-only. Below describes the hierarchy and purpose of the code.

* [thirdparty](//github.com/mashumafi/frontier/blob/main/src/thirdparty) - external libraries pulled stright from git
  * [cppfront](//github.com/mashumafi/frontier/blob/main/src/thirdparty/cppfront) - cpp2 compiler
  * [doctest](//github.com/mashumafi/frontier/blob/main/src/thirdparty/doctest) - testing framework
* [adapters](//github.com/mashumafi/frontier/blob/main/src/adapters) - wrappers for external libraries to either modernize or add high-level abstractions
* [groups](//github.com/mashumafi/frontier/blob/main/src/groups) - low level libraries
  * [csl](//github.com/mashumafi/frontier/blob/main/src/groups/csl/) - Chess Standard Library
    * [cslb](//github.com/mashumafi/frontier/blob/main/src/groups/csl/cslb) - basis classes used across most of the project
    * [csleh](//github.com/mashumafi/frontier/blob/main/src/groups/csl/csleh) - evaluation heuristics
    * [cslt](//github.com/mashumafi/frontier/blob/main/src/groups/csl/cslt) - transforms, mostly applies to encoding/decoding a position
    * [cslnnue](//github.com/mashumafi/frontier/blob/main/src/groups/csl/cslnnue) - efficiently updatable neural network
    * [cslai](//github.com/mashumafi/frontier/blob/main/src/groups/csl/cslai) - artificial interllegence
* [standalones](//github.com/mashumafi/frontier/blob/main/src/standalones) - libraries that apply business logic
* [applications](//github.com/mashumafi/frontier/blob/main/src/applications) - targets that output executables
  * [uci](//github.com/mashumafi/frontier/blob/main/src/applications/uci) - universal chess interface application

## Development

### VS Code

#### Dev Container

This project includes setup for Dev Containers in VS Code which should install everything needed for development.

#### CMake Extension

CMake features are available in the activity bar on the left or from the command palette. You can build and debug.

#### Testing

This project will be using [doctest](//github.com/doctest/doctest) to implement tests.

### Q & A

#### Why is the code not highlighted?

There is no syntax highlighter. The closest option is to use the C++ language mode to get some syntax and auto-complete. See [below](#why-dont-breakpoints-work) for instructions.

#### Why don't breakpoints work?

VS Code is probably not interpreting your file a C++ code. You can change the language mode with the command palette or find the option in the bottom-right corner of the editor.

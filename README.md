# "99 Bottles of Beer" kata in C++

[![CI](https://github.com/Coding-Cuddles/99-bottles-of-beer-cpp-kata/actions/workflows/main.yml/badge.svg)](https://github.com/Coding-Cuddles/99-bottles-of-beer-cpp-kata/actions/workflows/main.yml)
[![C++17](https://img.shields.io/badge/C%2B%2B-17-blue.svg)](https://en.cppreference.com/w/cpp/17)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Replit](https://img.shields.io/badge/Try%20with%20Replit-black?logo=replit)](https://replit.com/new/github/Coding-Cuddles/99-bottles-of-beer-cpp-kata)

## Overview

This kata complements [Clean Code: Advanced TDD, Ep. 24](https://cleancoders.com/episode/clean-code-episode-24-p1).

This repository contains an exercise to construct the entire
[99 Bottles of Beer](http://en.wikipedia.org/wiki/99_Bottles_of_Beer) song
using TDD.

### Exercise

Complete the `Bottles::song()` method that returns the lyrics for the song
"99 Bottles of Beer" as an **array of strings** where each string represents
a line of the song:

> 99 bottles of beer on the wall, 99 bottles of beer.</br>
> Take one down and pass it around, 98 bottles of beer on the wall.
>
> 98 bottles of beer on the wall, 98 bottles of beer.</br>
> Take one down and pass it around, 97 bottles of beer on the wall.
>
> ...
>
> 3 bottles of beer on the wall, 3 bottles of beer.</br>
> Take one down and pass it around, 2 bottles of beer on the wall.
>
> 2 bottles of beer on the wall, 2 bottles of beer.</br>
> Take one down and pass it around, 1 bottle of beer on the wall.
>
> 1 bottle of beer on the wall, 1 bottle of beer.</br>
> Take one down and pass it around, no more bottles of beer on the wall.
>
> No more bottles of beer on the wall, no more bottles of beer.</br>
> Go to the store and buy some more, 99 bottles of beer on the wall.

This is a C++17 kata using GoogleTest. Setup is complete when CTest reports
`100% tests passed`.

## Prerequisites

Required:

- [Git](https://git-scm.com/downloads)
- A compiler with C++17 support. Choose one:
  - [GCC](https://gcc.gnu.org/) 10+ on Linux
  - [LLVM Clang](https://llvm.org/) 14+ on Linux
  - [Apple Clang](https://developer.apple.com/xcode/) 17+ on macOS
  - [MSVC](https://visualstudio.microsoft.com/) 2022 on Windows
- [CMake 3.24 or later](https://cmake.org)

Optional:

- [GNU Make](https://www.gnu.org/software/make/), for shorter commands. Every
  required task also has direct CMake and CTest commands. Make may be
  unavailable on Windows.

You do not need to install GoogleTest separately. CMake finds an installed
copy or downloads the pinned release when needed.

## Set up the kata

The tracked Replit configuration and badge are retained. The local setup below
is the validated development path.

1. Clone the repository:

   ```console
   git clone https://github.com/Coding-Cuddles/99-bottles-of-beer-cpp-kata.git
   ```

2. Enter the repository directory:

   ```console
   cd 99-bottles-of-beer-cpp-kata
   ```

3. Build and run the tests. Use Make when it is installed:

   ```console
   make test
   ```

   Otherwise, use CMake and CTest directly:

   ```console
   cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug
   cmake --build build --config Debug
   ctest --test-dir build --build-config Debug --output-on-failure
   ```

The first run may download and build GoogleTest. CTest should report
`100% tests passed`. If a command reports a missing compiler or CMake, install
that prerequisite and run the setup commands again. Setup is complete when
CTest reports `100% tests passed`.

## Work on the kata

Add one test at a time to `test_bottles.cpp`, then implement enough code in
`bottles.h` to make the test pass. Keep the exercise and expected lyrics above
as the target behavior.

After each change, use Make when it is installed:

```console
make test
```

Otherwise, use CMake and CTest directly:

```console
cmake --build build --config Debug
ctest --test-dir build --build-config Debug --output-on-failure
```

Continue when CTest reports `100% tests passed`.

## Run the example

Use Make when it is installed:

```console
make run
```

Otherwise, use the CMake run target:

```console
cmake --build build --config Debug --target run
```

The executable prints `Hello World!`.

## Make command reference

Make is optional. Run `make` or `make help` to list these commands in the
terminal.

| Command             | Result                                    |
| ------------------- | ----------------------------------------- |
| `make all`          | Build and run the test suite              |
| `make help`         | List public Make targets                  |
| `make build`        | Configure and build without running tests |
| `make run`          | Build and run the example executable      |
| `make test`         | Build and run the test suite              |
| `make format`       | Format tracked C++ and header files       |
| `make format-check` | Check formatting without changing files   |
| `make clean`        | Remove generated build artifacts          |

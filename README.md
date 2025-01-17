# ChessEngine

[![C++ build](https://github.com/ryan597/chessengine/actions/workflows/build_and_test.yml/badge.svg)](https://github.com/ryan597/chessengine/actions/workflows/build_and_test.yml)
[![cpp-linter](https://github.com/ryan597/chessengine/actions/workflows/cpp-linter.yml/badge.svg)](https://github.com/ryan597/chessengine/actions/workflows/cpp-linter.yml)

C++ chess engine

Beginning of a project to build my own chess engine along with GUI for playing against the engine.

First tasks:

- Design base classes for the board representation
- Enable pieces to move
- Generate all legal moves (if in check etc.)
- Update PGN with notations
- Basic GUI with pieces and ability to move them
- Create tests for implemented classes and methods

## Building

Using the included `CMakeLists.txt` file.

```bash
git clone https://github.com/ryan597/chessengine.git
cd chessengine
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build
```

## Testing

This project will use the `Catch2` testing framework for C++ unit tests.

- [Catch2 github](https://github.com/catchorg/Catch2/tree/devel)
- [Tutorial on Catch2 here](https://github.com/catchorg/Catch2/blob/devel/docs/tutorial.md#top)
- [More examples](https://github.com/catchorg/Catch2/blob/devel/docs/list-of-examples.md)

You can install Catch2 (v3) with the following

```bash
git clone https://github.com/catchorg/Catch2.git
cd Catch2
cmake -B build -H. -DBUILD_TESTING=OFF
sudo cmake --build build/ --target install
```

Tests can be run after building

```bash
cd chessengine
cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug
cmake --build build
cd build && make test
```

To generate the `CodeCoverage` report you need to have installed `lcov` and `gcovr`, then you can make the target

```bash
make coverage
```

The coverage report is viewable by opening the file `./build/coverage/index.html` in a web browser

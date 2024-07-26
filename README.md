UM Chess
==========
### UCI Chess Engine

UM Chess is a chess program for Windows, Linux, Mac OS, Android and Raspberry Pi, is a console-based chess engine for use with [xboard][4], [Arena][5], [Tarrasch][6], [Droidfish][7] or any UCI-compatible GUI. UM Chess is also a javascript library to play with [chessboardjs][8] or any js GUI.

- [Play on line](https://gekomad.github.io/Cinnamon/)

Version
----------
2.5

News
----------
- Time management
- Tapered eval




Features
----------

- [Elo ratings][3]
- Available for both Unix, Windows, Mac, Android, ARM and Javascript
- UCI protocol
- GPL 3 License
- Chess 960
- C++11 source
- PVS
- Rotated bitboards
- Null moves
- Futility pruning
- Reverse Futility Pruning
- Delta pruning
- Razoring
- Interruptible multithread Perft test [standard][9] and [chess960][10]
- 32/64 bit architectures
- Iterative deeping
- History heuristics
- Killer heuristics
- Lazy evaluation
- MVV/LVA
- Transposition Table
- Aspiration Windows
- Late Move Reduction
- Ponder
- Gaviota Tablebases
- Syzygy Tablebases

Binaries
----------

Binaries are available [here][1].
All files are compiled statically, no further libraries are necessary.

Command line tools
----------
#### Perft
`UM Chess.exe -perft [-d depth] [-c nCpu] [-h hash size (mb) [-F dump file]] [-Chess960] [-f "fen position"] `

Setting `-F` and `-h` you can stop (Ctrl-c) and restart the perft process.


#### Gaviota DTM (distance to mate)

`UM Chess.exe -dtm-gtb -f "fen position" -p path`

#### Gaviota WDL (win/draw/loss)

`UM Chess.exe -wdl-gtb -f "fen position" -p path`

#### SYZYFY DTZ (distance to zero)

`UM Chess.exe -dtz-syzygy -f "fen position" -p path`

#### SYZYFY WDL (win/draw/loss)

`UM Chess.exe -wdl-syzygy -f "fen position" -p path`

#### EPD generator
`UM Chess.exe -puzzle_epd -t K?K?`

 example: `UM Chess.exe -puzzle_epd -t KRRKPN`

Compiling
---------

UM Chess requires C++11 or greater

- use MS Visual Studio (UM Chess.vcxproj)

- use cmake (CMakeLists.txt)

- use make - unique Makefile to compile for many architectures:


```
    $ make


    Makefile for cross-compile Linux/Windows/OSX/ARM/Javascript

    make UM Chess64-modern-INTEL     > 64-bit optimized for modern Intel cpu
    make UM Chess64-BMI2             > 64-bit optimized for Haswell Intel cpu
    make UM Chess64-modern-AMD       > 64-bit optimized for modern Amd cpu
    make UM Chess64-modern           > 64-bit with popcnt bsf sse3 support
    make UM Chess64-generic          > Unspecified 64-bit
    make UM Chess64-ARM              > Optimized for ARM cpu

    make UM Chess32-modern           > 32-bit with sse support
    make UM Chess32-generic          > Unspecified 32-bit
    make UM Chess32-ARM              > Optimized for ARM cpu

    make UM Chess-js                 > Javascript build

    add:
     COMP=compiler                   > Use another compiler
     FULL_TEST=yes                   > Unit test (googletest)


    g++ is the default compiler, add COMP=yourcompiler to use another compiler
     example: make UM Chess64-modern-INTEL COMP=clang++

```

License
-------

UM Chess is released under the GPLv3+ license.



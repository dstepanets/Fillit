# Fillit

A variant of Tetris game. Fit a set of Tetrimino pieces into the smallest possible square.

![](fillit_demo.gif)

## Description

The program takes a set of [Tetriminos](https://en.wikipedia.org/wiki/Tetromino). And fits them into the smallest possible square, without rotation.

A tetrimino is defined like this, on a 4x4 square:

```
....
..##
.##.
....
```

An input file can contain up to 26 such pieces, separated by empty lines. On a solution map pieces are marked by letters in alphabetical order:

```
ABBBB.
ACCCEE
AFFCEE
A.FFGG
HHHDDG
.HDD.G
```

*This is the project of the Algorithms branch of the School 42 curriculum.*

**Detailed description of the task: [fillit.en.pdf](https://github.com/dstepanets/Fillit/blob/master/fillit.en.pdf)**

## Usage

Compile with `make`. Run like this:

```
./fillit <tetriminos_file>
```

You can use `test_files` or create your own.

## Algorithm

Simple backtracking was enough for this exercise. First, we count tetriminos and create the smallest map on which this number of 4-square pieces could theoretically fit. Then place them one by one, trying all combinations, and returning to the previous piece if the current one doesn't fit anywhere.

Once we tried all pieces in all positions and haven't found the solution, we extend our map by one and start all over.

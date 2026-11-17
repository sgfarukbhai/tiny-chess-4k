# Tiny Chess 4K

A chess engine in 4,096 bytes of Python, written from scratch for the [make.fun tiny-chess-01 bounty](https://make.fun/bounty/tiny-chess-01).

[![tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/sgfarukbhai/tiny-chess-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/sgfarukbhai/tiny-chess-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01)

## Engine

`main.py` (4,084 bytes) is a self-contained 0x88 chess engine: alpha-beta search with quiescence, a transposition table, MVV-LVA + killer move ordering, an incremental material + piece-square-table evaluation, and a passed-pawn bonus. It searches to a fixed 50,000-node budget per move and talks to the make.fun environment over HTTP (UCI moves).

The source is an LZMA-compressed payload with a tiny unpacker (the compressed form counts toward the 4,096-byte cap). The readable development version lives in the build log of the workspace, not in this repo.

## Local practice results

| trial | result | Elo |
|---|---|---|
| 0 | 2W 1D 3L | 1191 |
| 1 | 4W 0D 2L | 1451 |
| 2 | 4W 1D 1L | 1545 |

Mean Elo **1396** on the 6-game practice gauntlet, vs the house baseline (sunfish 4k) mean of 1365 — a lead of +31. The engine clears the 1154 practice floor and beats the baseline, but the prize gate (~+125 lead) is not assured; grading decides.

## License

MIT. Created by SG Faruk Bhai.

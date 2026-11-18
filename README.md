# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/wanara11/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/wanara11/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A tiny chess engine in 4 KB of Python: 0x88 board, negamax alpha-beta with a transposition table, MVV-LVA + killer + history move ordering, quiescence search, null-move pruning, check extensions and iterative deepening on a fixed node budget — fully deterministic, no clock, no randomness, standard library only. It plays through the make.fun env (`MAKEFUN_ENV_URL`) and answers each position with its best move.

## The engine

- **Board**: 0x88, signed pieces, full legal move generation (castling, en passant, all promotions), perft-verified.
- **Search**: negamax alpha-beta, transposition table (Zobrist), killer + history heuristics, null-move pruning (R=2), check extensions, quiescence on captures/promotions and all replies to check.
- **Evaluation**: material + piece-square tables + bishop pair + endgame king table, mate-distance scoring.
- **Budget**: fixed 80,000 nodes per move, so every trial replays move-for-move.

## Run it

`main.py` is the whole engine. It needs the make.fun trial environment:

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:PORT python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=9f9brj56&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>

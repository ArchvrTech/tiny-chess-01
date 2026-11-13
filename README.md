# tiny-chess-01

A tiny chess engine in 4,092 bytes of Python, built by an AI agent for the
make.fun bounty "Build the strongest chess engine in 4 KB of Python"
(tiny-chess-01, $500 in USDC on Solana).

`main.py` is the whole engine: 0x88 board, alpha-beta search with quiescence,
transposition table, MVV-LVA + history move ordering, null-move pruning and
check extensions, with a fixed node budget of 120,000 nodes per move.
Standard library only, no model calls, no network beyond the trial env.

Practice Elo (local grading, 3 trials): 1087 / 1396 / 1253, mean 1245.

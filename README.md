# tiny-chess-01 v10

A tiny chess engine in 4,095 bytes of Python, built by an AI agent for the
make.fun bounty "Build the strongest chess engine in 4 KB of Python"
(tiny-chess-01, $500 in USDC on Solana).

`main.py` is the whole engine: 0x88 board, alpha-beta + quiescence search with
a transposition table, tapered midgame/endgame piece-square tables, bishop-pair
and passed-pawn bonuses, king pawn-shield, doubled-pawn penalty and rook on
open-file bonus, LMR + PVS, null-move pruning, check extensions and killer
move ordering, with a fixed node budget of 120,000 nodes per move. Standard
library only, no model calls, no network beyond the trial env. Fully
deterministic: no wall clock, no unseeded randomness.

Practice Elo (local grading, 3 trials): 2112 / 2112 / 1654, mean 1959.
Trial-0 (the official practice grade): 2112, 6 wins / 0 draws / 0 losses.
v8 scored 1809 on trial-0.

## Local trials (kit scorer, 6 games each)

- trial-0: Elo 2112, 6W/0D/0L, all six games won by checkmate, wall 1173s, spare plies 523.
- trial-1: Elo 2112, 6W/0D/0L, all six games won by checkmate, wall 1248s, spare plies 497.
- trial-2: Elo 1654, 5W/0D/1L; the sole loss was game 6 as black against the nodes-500k opponent, wall 1081s, spare plies 481.
- Mean Elo 1959 across the three trials, well above the sunfish practice baseline of 1325.
- 2112 is the maximum possible score for a single trial: winning every game caps the Elo there.

#tiny-chess-01

A tiny chess engine in 4,075 bytes of Python, built by an AI agent for the
make.fun bounty "Build the strongest chess engine in 4 KB of Python"
(tiny-chess-01, $500 in USDC on Solana).
main.py is the whole engine: 0x88 board, alpha-beta + quiescence search with
a transposition table, tapered midgame/endgame piece-square tables, bishop-pair
and passed-pawn bonuses, LMR + PVS, null-move pruning, check extensions and
killer/history move ordering, with a fixed node budget of 100,000 nodes per
move. Standard library only, no model calls, no network beyond the trial env.
Practice Elo (local grading, 3 trials): 1598 / 1396 / 1253, mean 1416.

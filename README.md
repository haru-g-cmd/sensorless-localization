# Sensorless Localization

A bot is placed on a 15x15 grid maze but has no idea where it is and has no sensors. The goal is to find a sequence of moves that guarantees the bot knows its exact position by the end, regardless of where it started. Maze is randomly generated at runtime.

The bot starts with a belief state containing every open cell on the map. Each move shrinks this set: when the bot moves north, every position in the belief set either shifts up or stays put if there's a wall. Different positions can collapse onto the same cell, which reduces the set size.

The search uses greedy best first with belief set size as the heuristic. It explores directions that produce the smallest belief sets first. Once the set hits size 1, the bot knows exactly where it is. The output shows the full move sequence with the belief set shrinking at each step.

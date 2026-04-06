# L-Tromino Tiling Puzzle

An interactive web-based simulation that lets you explore one of the most beautiful results in combinatorial mathematics: **any 2^n x 2^n grid with one square removed can always be perfectly tiled using L-shaped trominoes.**

[**Try it live**](https://michaellomuscio.github.io/L-Tromino-Tiling-Puzzle/)

## What is an L-Tromino?

An L-tromino is an L-shaped piece that covers exactly **3 squares**. It looks like this:

```
██
█
```

## The Puzzle

Take a grid whose dimensions are a power of 2 (2x2, 4x4, 8x8, 16x16, ...). Remove **any single square** from the grid. The claim is that the remaining squares can **always** be perfectly tiled with L-trominoes — no gaps, no overlaps — regardless of which square you remove.

### Why the numbers work

A 2^n x 2^n grid has 4^n squares. Remove one, and you have 4^n - 1 remaining. Since each L-tromino covers 3 squares:

| Grid Size | Total Squares | After Removal | L-Trominoes Needed |
|-----------|--------------|---------------|-------------------|
| 2x2       | 4            | 3             | 1                 |
| 4x4       | 16           | 15            | 5                 |
| 8x8       | 64           | 63            | 21                |
| 16x16     | 256          | 255           | 85                |

The fact that 4^n - 1 is always divisible by 3 is itself a nice little proof exercise!

## The Big Idea: Recursion

The proof that this tiling always works uses a beautiful **divide-and-conquer** strategy:

1. **Split** the board into 4 equal quarters
2. The removed square is in **one** of the quarters
3. Place a single L-tromino at the center, covering one cell from each of the **other three** quarters
4. Now every quarter has exactly one "occupied" cell — each is a smaller version of the same puzzle!
5. **Repeat** until you reach 2x2 boards, which are trivial

This recursive structure is closely related to **fractals** — the same pattern repeating at every scale.

## Features

### Free Play Mode
- Choose grid sizes from 2x2 to 16x16
- Click any square to remove it
- Place L-trominoes by hovering and clicking
- Rotate pieces with the **R** key
- Undo with **Z**
- Full touch support for tablets

### Watch the Recursive Solution
- Animated step-by-step visualization of the recursive algorithm
- **Quadrant overlays** show which sub-problem the algorithm is currently solving, so you can literally *see* the divide-and-conquer in action
- **Depth-based coloring** — pieces are colored by recursion depth (gold, green, blue, pink), making the fractal structure visible in the final tiling
- Adjustable animation speed

### Guided Discovery Mode
A step-by-step walkthrough that scaffolds the "aha moment":
1. Start with a small board
2. Try tiling it yourself
3. See the quadrant split visualized
4. Place the key center piece
5. Realize each quarter is a smaller copy of the same puzzle
6. Watch the insight generalize to larger boards

### Hint System
Stuck? The hint button places the next piece from the recursive solution, helping you get unstuck without giving away the whole answer.

## How to Use

Just open `index.html` in any modern web browser, or visit the [live version](https://michaellomuscio.github.io/L-Tromino-Tiling-Puzzle/). No dependencies, no build step, no server required — it's a single self-contained HTML file.

## Context

This was built as a teaching tool for working with an advanced elementary-level math student. The L-tromino tiling puzzle is an ideal topic because it:

- Is **accessible** — the rules are simple enough for a 4th grader
- Is **surprising** — "it works for ANY removed square" is a genuinely shocking result
- Teaches **proof by recursion** — a powerful mathematical technique, presented visually
- Connects to **fractals** — the recursive structure is self-similar at every scale
- Builds **mathematical reasoning** — the student can discover the pattern before being told the answer
- Involves **hands-on problem solving** — it's a puzzle, not a lecture

## License

MIT

# Tiling Puzzles

Interactive web-based simulations exploring beautiful results in combinatorial mathematics — built as teaching tools for advanced elementary math students.

[**Try the L-Tromino Puzzle**](https://michaellomuscio.github.io/L-Tromino-Tiling-Puzzle/) | [**Try the Domino Challenge**](https://michaellomuscio.github.io/L-Tromino-Tiling-Puzzle/domino-challenge.html)

---

# Puzzle 1: L-Tromino Tiling

**Any 2^n x 2^n grid with one square removed can always be perfectly tiled using L-shaped trominoes.**

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

### Extension: Try Other Shapes!
The L-tromino is the star of the puzzle, but a shape selector lets you experiment with other pieces — **Straight Tromino (I), Domino, T-Tetromino, and Square**. Can you tile the board with a different shape? Why do some shapes work and others don't? What's special about the L? These become natural follow-up questions once the main puzzle clicks.

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

---

# Puzzle 2: The Mutilated Chessboard (Domino Challenge)

**Remove two squares from an 8x8 chessboard. Can you tile the rest with dominoes? Sometimes yes, sometimes no — and the reason is beautiful.**

## The Puzzle

A domino covers exactly 2 adjacent squares. A standard 8x8 board (64 squares) can be tiled with 32 dominoes. But what if you remove 2 squares first?

- **Remove two opposite corners** (same color) → **IMPOSSIBLE**
- **Remove two adjacent corners** (different colors) → **ALWAYS POSSIBLE**

## The Proof (The Coloring Argument)

Color the board like a chessboard. Every domino — horizontal or vertical — always covers exactly **one dark square and one light square**. So 31 dominoes need exactly 31 dark and 31 light squares.

- Two opposite corners are the **same color** → removing them leaves 32 of one color and 30 of the other → **impossible!**
- Two squares of **different colors** → removing them leaves 31 and 31 → **possible!**

This is one of the most elegant impossibility proofs in mathematics — accessible to anyone who can count.

## Features

### Five Challenge Modes
- **Free Play** — remove any 2 squares you choose
- **Opposite Corners** — the classic impossible case
- **Adjacent Corners** — the classic possible case
- **Same-Color Pair** — pick any two same-colored squares (always impossible)
- **Different-Color Pair** — pick any two different-colored squares (always possible)

### The Coloring Reveal
The key "aha moment" — click "Show Chessboard Coloring" to reveal the hidden pattern. The board lights up with vivid colors and displays a live count of remaining dark vs. light squares, making the impossibility (or possibility) immediately visible.

### Domino Placement
- Place horizontal or vertical dominoes with hover preview
- Rotate with **R** key
- Undo with **Z**
- Full touch support

### Extension: Try Other Shapes!
Dominoes are the focus of the coloring argument, but you can also experiment with **L-Trominoes, Straight Trominoes, T-Tetrominoes, and Squares**. Does the same-color impossibility still apply with other pieces? (Hint: the coloring argument is specific to dominoes — explore why!)

---

## How to Use

Open `index.html` (L-Tromino) or `domino-challenge.html` (Domino Challenge) in any modern web browser, or visit the live versions above. No dependencies, no build step, no server required — they are self-contained HTML files.

## Why These Two Puzzles Together?

These puzzles are perfect companions because they teach opposite lessons:

| | L-Tromino Puzzle | Domino Challenge |
|---|---|---|
| **Result** | Always possible | Sometimes impossible |
| **Key technique** | Constructive proof (recursion) | Impossibility proof (invariant) |
| **Big idea** | Divide and conquer | Parity / coloring arguments |
| **Connection** | Fractals, self-similarity | Combinatorics, proof by contradiction |

Together they show that math isn't just about calculating answers — it's about understanding **why** things work (or don't).

## Context

Built as teaching tools for working with an advanced elementary-level math student. Both puzzles are:

- **Accessible** — simple rules, no prerequisites beyond basic arithmetic
- **Surprising** — the results are genuinely unexpected
- **Visual** — the proofs can be *seen*, not just read
- **Hands-on** — puzzles, not lectures
- **Deep** — they introduce proof techniques used throughout mathematics

## License

MIT

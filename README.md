# Set Cover – Local Search with Random Restarts

Lab 1 of the **Computational Intelligence** course (2024, Politecnico di Torino, Prof. Giovanni Squillero).

## The problem
The [Set Cover problem](https://en.wikipedia.org/wiki/Set_cover_problem): given a universe of elements and a collection of sets, each with a cost, pick the cheapest group of sets that together covers every element. It is NP-hard, so the goal is a good solution rather than a guaranteed optimal one.

## My approach
**Hill climbing with random restarts:**
- A solution is a boolean vector: which sets are selected.
- **Tweak:** flip one random set in or out.
- **Best neighbor:** generate several tweaks and keep the best one.
- **Fitness:** first validity (does it cover the whole universe?), then lowest cost.
- **Restarts:** run the climb several times from different random starting points and keep the best result, to avoid getting stuck in a local optimum.
- The cost at each step is plotted to show convergence.

## Results
| Case | Sets | Universe | Density | Best cost found |
|------|------|----------|---------|-----------------|
| 1 | 10 | 100 | 0.2 | ~290 |
| 2 | 100 | 1,000 | 0.2 | ~34,378 |
| 3 | 1,000 | 10,000 | 0.2 | ~124,788 |

Cases 4–6 (10,000 sets × 100,000 elements) are included in the notebook but were too large to run on my machine's memory.

## How to run
Open `set-cover.ipynb` in Jupyter or Google Colab.
Requirements: `numpy`, `matplotlib`, `icecream`.

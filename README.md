## Introduction

This project utilizes a Genetic Algorithm, a search heuristic inspired by natural selection, to solve a maze. The algorithm evolves a population of potential solutions (paths) over generations, gradually improving their ability to navigate the maze and reach the goal.

## How it Works

### Maze Representation

The maze is represented using a 2D list (a list of lists) where:

- `0` represents an open path that can be traversed.
- `1` represents a wall or obstacle that blocks movement.

### Individual Representation

Each individual in the GA's population represents a potential solution to the maze. An individual is encoded as a sequence of movements, where each movement is represented by a character:

- `U`: Move Up
- `D`: Move Down
- `L`: Move Left
- `R`: Move Right

This sequence of movements defines the path the individual attempts to take through the maze.

### Fitness Function

The fitness function evaluates how well an individual solves the maze. In this case, the fitness is determined by the individual's proximity to the maze's goal (end point).  

- **Lower fitness values are better.** An individual that reaches the goal has a fitness of 0, indicating a perfect solution.
- Individuals that do not reach the goal receive a fitness score based on the Manhattan distance between their final position and the goal. The shorter the distance, the better the fitness.

### Genetic Operators

The GA employs three primary operators to evolve the population:

1. **Selection:** Tournament selection is used to select individuals for reproduction. In a tournament, a small number of individuals are randomly chosen, and the individual with the best fitness (lowest score) is selected as a parent.

2. **Crossover:** Uniform crossover is applied to two parent individuals to create offspring. In uniform crossover, each gene (movement direction) in the offspring is randomly chosen from either parent. This process combines genetic material from successful individuals to potentially create even better solutions.

3. **Mutation:** Custom mutation is introduced to maintain diversity in the population and explore new areas of the search space. It randomly changes individual genes (movement directions) with a certain probability. This helps prevent the algorithm from getting stuck in local optima.

### Evolution

The GA iterates through a fixed number of generations. In each generation:

1. Offspring are created through selection, crossover, and mutation.
2. The fitness of each offspring is evaluated.
3. The population is updated, typically by replacing less fit individuals with the new offspring.

This iterative process gradually improves the average fitness of the population, leading to solutions that effectively navigate the maze.

### Visualization

Matplotlib is used to visualize the maze and the best path found by the GA in each generation. The visualization provides a clear representation of the algorithm's progress and the evolving solution.

## Dependencies

- `matplotlib`: For plotting the maze and the path found by the GA.
- `deap`: For implementing the Genetic Algorithm framework, providing tools for creating individuals, populations, and genetic operators.

## How to Run

1. **Open the notebook in Google Colab.**
2. **Execute all the cells in the notebook.** The cells contain the code to define the maze, set up the GA, run the evolution process, and visualize the results.

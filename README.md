
# Genetic Algorithm for Traveling Salesman Problem (TSP)

This repository contains an implementation of a Genetic Algorithm (GA) to solve the **Traveling Salesman Problem (TSP)** using Python. The TSP is a classic optimization problem where the goal is to find the shortest route for a salesman to visit a set of cities and return to the starting point.

---

## **Features**
- **Encoding Scheme**: Permutations are used to represent city routes.
- **Fitness Function**: Calculates the total distance of a route, including the return to the starting city.
- **Genetic Operators**:
  - **Selection**: Tournament selection to favor fitter solutions.
  - **Crossover**: Partially Matched Crossover (PMX) to combine parent routes while ensuring valid permutations.
  - **Mutation**: Randomly swaps two cities in the route to maintain diversity.

---

## **Dependencies**
The following Python libraries are required:
- **numpy**: For mathematical operations.
- **DEAP**: A framework for evolutionary algorithms.
- **random**: For generating random sequences.
- **matplotlib**: For visualization (if used).

Install dependencies using:
```bash
pip install deap numpy matplotlib
```

---

## **How It Works**
1. **Initialization**: Generate a population of random routes.
2. **Fitness Evaluation**: Calculate the total distance for each route.
3. **Selection**: Use tournament selection to choose the best routes for reproduction.
4. **Crossover and Mutation**: Combine and mutate routes to create new solutions.
5. **Evolution**: Iterate over generations to improve the population.
6. **Output**: The algorithm outputs the best route and its total distance.

---

## **Results**
- The genetic algorithm successfully finds a solution with a total distance of **2085**, which matches the optimal distance for the provided TSP data.
- The route order may vary while maintaining the same minimal distance, as the TSP solution is cyclic.

---

## **Code Highlights**
- **Fitness Function**: Evaluates the total distance of a route:
  ```python
  def evalTSP(individual):
      distance = distance_map[individual[-1]][individual[0]]  # Distance from last city to first
      for i in range(len(individual) - 1):
          distance += distance_map[individual[i]][individual[i + 1]]
      return distance,
  ```
- **DEAP Framework**: Used to handle population initialization, genetic operations, and evolution.

---

## **Customization**
- Update the `distance_map` with your own city distances for a custom TSP problem.
- Adjust parameters like population size, crossover probability, mutation probability, and generations for experimentation.

---

## **About This Project**
This code is part of my **MSc Artificial Intelligence** course, focusing on optimization techniques and evolutionary computation.

---

## **Acknowledgments**
- Framework: [DEAP Documentation](https://deap.readthedocs.io/)
- This project was created by using academic materials from the **CS5707 Artificial Intelligence** course.

---

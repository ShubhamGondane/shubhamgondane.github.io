---
title: 'Bi-directional search applied to Pacman and Rubiks cube problem'

permalink: /projects/bi-directional
tags:
  - Bidirectional Search
  - Breadth First Search
  - Depth First Search
  - Iterative deepening
  - A* algorithm
  - Pacman
  - Artificial Intelligence
---

Traditional search techniques like Breadth First Search(BFS) and Depth First Search(DFS) work very well in a small search space but as the search space grows so does tht time complexity of these techniques. Often in large search space these algorithms run in exponential time. A way to combat this issue is to use Bidirectional search algorithm.

This project explores the performance of bi-directional search to BFS, DFS and A* algorithm in the Pacman food pellet search algorithm. Further bi-directional search is used to search a solution to the Rubiks cube problem. We introduce bi-directionality to the iterative deepening A* algorithm.

Solving a rubiks cube is quite difficult. In fact, there are 4.3252 x 10^19 different states that can be reached from any given configuration.Iterative deepening A* algorithm can be used to solve this problem.

Iterative deepening A*
------

Iterative deepening A* (IDA\*) is a graph traversal and path search algorithm that can find the shortest path between a designated start node and any member of a set of goal nodes in a weighted graph. It is a variant of iterative deepening depth-first search that borrows the idea to use a heuristic function to evaluate the remaining cost to get to the goal from the A* search algorithm. 

Rubiks cube representation
<br/><img src='/images/rubiks_cube_state.png'>

State space
-----
A Cube Node consists of 4 parts:

- State: Which is represented as a string indicating the position of 54 cubies.
- Heuristic.
- g-value: For calculating bound of the search algorithm.
- Path: Sequence of actions taken from initial state to reach the current state.

Action space
-----

- The cube can only be rotated in clockwise direction.
- Every action corresponds to a colored face being rotated clockwise.
- Every face can be rotated upto three times in clockwise direction
- An action is represented by pair: <Color, Number of Rotations (i.e. 1 every time)> An example of an action sequence is : R1W1Y1

Heuristic
-----

For each cubic, compute the minimum number of moves required to correctly position and orient it, and sum these values over all cubies. The heuristic considered here is to take the maximum of the sum of the Manhattan distances of the corner cubies, and the edge cubies, each divided by four.

Consider the eight corner cubies, the position and orien- tation of the last cubic is deter- mined by the remaining seven, so there are exactly 8! x 37 = 88,179,840 possible combinations. Using a breadth-first search from the goal state, these states can be enumerated, and record in a table the number of moves required to solve each combination of corner cubies.

Similarly, if we consider the 12 edge cubies, the number of possible combinations for six of the twelve edge cubies is 12!/6! x 26 = 42,577,920. Compute the corresponding heuris- tic table for the remaining six edge cubies. The heuristic used for the our implementation is the maximum of all three of these values: all eight corner cubies, and two groups of six edge cubies each.


Algorithm
-----

	while Solution is not found do

		while Both the priority queues are not empty do

			Select node from the TD queue 

			if Not explored earlier then

				add in explored

				add its state in path

				if BU path contains the current node then

					Find out the node in BU explored

					return Both the nodes 

				end if

				Generate successors if they are not explored add them in the priority queue

			end if

		end while

	end while


You can find the entire project and the report 
[here](https://github.com/ShubhamGondane/bidirectional "Github link")


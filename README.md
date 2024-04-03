# QAOA MaxCut Solver

Given an undirected unweighted graph, the 2-MaxCut problem can be stated as the problem of partitioning the nodes of a graph into two subsets such that the numberof edges between them is as large as possible.

...

The QAOA algorithm provides an approximate solution to the MaxCut problem. Here are some highlights from our results:

- **Graph**: The algorithm was tested on a graph with 4 nodes and 4 edges.
- **Exact Solution**: The exact solution was found using a classical eigensolver. The optimal cut had a value of X.
- **QAOA Solution**: The QAOA algorithm found a cut with a value of Y. This demonstrates that the QAOA algorithm can find near-optimal solutions to the MaxCut problem.

Here is a comparison of the exact and QAOA solutions:

![Comparison](images/comparison.png)

The above figure shows the graph with the vertices colored according to the optimal cut (left) and the cut found by the QAOA algorithm (right).

...

# QAOA MaxCut Solver

Given an undirected unweighted graph, the 2-MaxCut problem can be stated as the problem of partitioning the nodes of a graph into two subsets such that the numberof edges between them is as large as possible.

This repository https://github.com/SophiaZhyrovetska/qaoa-maxcut contains the previous version of the QAOA max-cut solver case. However, when you try to reproduce or run it you may find errors in 
* either minimization function when printing out the best solution
* or type error as alpha is given a float value but is being an array when priniting out `result`.

I have reproduced this repo and find out where the exact error was

* First: The parameters *params* were not taking a singular value but taking an array as alpha = theta[1:] and beta = theta[:1] in the get_cost_function(G). While the you can see the correct part implemented in notebook ('qaoa-maxcut.ipynb')
  as
  corrected:
  `def cost_function(theta):
        alpha = theta[1:][0]
        beta = theta[:1][0]`
  Mistake:
   `def cost_function(theta):
       `alpha = theta[1:]
        #beta = theta[:1]`
The `rz` gate takes a single float value as its rotation angle so you declare alpha as mentioned above `alpha = theta[1:][0]`
* Then when passing the parameters as arguements params[1:][0], params[:1][0] to evaluate get_frequencies_for_optimal_circuit()

The QAOA algorithm provides an approximate solution to the MaxCut problem. Here are some highlights from our results:

- **Graph**: The algorithm was tested on a graph with 4 nodes and 4 edges.
- **Exact Solution**: The exact solution was found using a classical eigensolver. The optimal cut had a value of X.
- **QAOA Solution**: The QAOA algorithm found a cut with a value of Y. This demonstrates that the QAOA algorithm can find near-optimal solutions to the MaxCut problem.

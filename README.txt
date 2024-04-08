1) What do you think are the advantages or disadvantages of this dynamic programming solution.

One of the advantages is that it divides the problem into subproblems which solves for all values less than k. Additionally, it also avoids brute forcing all
the different combination of sets which helps it achieve a sub-exponential time as long as the k is not far off from n.

One of the disadvantages is that it is unable to detect all of the subsets that is equal to k. 
In the lecture, the algorithm skipped over the subset {3, 7} because directly above the cell of 7 is 5, which was set to 1 -- a valid solution,
which led to 7 being skipped. Another disadvantage is that it continues to compute for the other members of the set even if one valid subset has already been found,
however this can be easily fixed by checking if the rightmost cell has been set to 1. Lastly, another disadvantage that I have noticed is that for n = {1, 2, 65, 169} and k = 237,
it creates almost a thousand cells before computing the subset, while brute forcing it should only take a few tries to know that the answer is the set itself. In other words, it does
bad if k is too high while n is low.


2) What is the running time of this dynamic programming solution?
For a set size of n and sum k, the algorithm creates an array of n * k size. Each cell filled up needs to check the the cell above and
the cell on their left S blocks away, where S is the member of the set. Filling up the cell requires constant time as it does not scale
in complexity for each cells: it is simply comparing two values in constant-time computable memory addresses. The backtracking can be done
in linear time as it scales with the size of the set. Therefore, the running time of the algorithm is O(n*k).
# Root to Leaf Paths

1. Push the current node in a path array

2. If it is a leaf node:
   
   1. Push it in the final answer array
   
   2. Pop the last element
   
   3. Return

3. Else recursively call the solve method for left and right subtree.

4. Once we return from our calls, we can pop_back the last element of the path array as we are about to backtrack



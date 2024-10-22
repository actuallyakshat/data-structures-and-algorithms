# Bottom View and Top View

Crux : Maintain a  map to store the level (horizontal) and the node that appeared on, that level, overwrite the value of node for each level when you encounter a new element so that we have the last seen node for each horizontal distance from the root, ie. bottom view

Note: Don't overwrite the map and you will get the top view instead.

**Algorithm:**

**Step 1:** Create a vector `ans` to store the result. Check if the tree is empty. If it is, return an empty vector.

**Step 2:** Create a map to store the top view of nodes based on their vertical positions. The key of this map is the vertical index and the value is the node’s data.

**Step 3:** Initialise a queue to perform breadth first traversal. Each element of this queue is the node of the binary tree along with its vertical coordinate. Enqueue the root node into the queue with its vertical position initialised to 0.

![](https://static.takeuforward.org/content/bottom-view-tree-image4-cDdroXLo)

**Step 4:** While the queue is not empty, pop the front node of the queue and for this node:

1. Get its vertical position. If this vertical position is not in the map, add the node’s data to the map. This means that this node is the first node encountered at this vertical position during the traversal.
2. If the vertical position of this node is already a key in the map, it implies that a node higher in the tree with the same vertical position has already been processed. Overwrite this position with the current node as we want to get the lowest node of that vertical index.
3. Enqueue the left child with a decreased vertical position ie. current vertical index -1. As when we move to the left child, we are moving towards the left column in the vertical order traversal.
4. Enqueue the right child with an increased vertical position ie. current vertical index + 1. As when we move to the right child, we are moving towards the right column in the vertical order traversal.

![](https://static.takeuforward.org/content/bottom-view-tree-image5-xhvadXBe)

**Step 5:** Iterate over the map and push the values of each node into the top view traversal.

1. Since the keys of the map are sorted based on their keys (vertical positions), the nodes added to the `ans` vector will be sorted left to right.
2. Return the ‘ans’ vector.

![](https://static.takeuforward.org/content/bottom-view-tree-image6-dhWJO6Qn)

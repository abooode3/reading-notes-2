### Trees

* Common Terminology

- Node - A Tree node is a component which may contain it’s own values, and references to other nodes
- Root - The root is the node at the beginning of the tree
- K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
- Left - A reference to one child node, in a binary tree
- Right - A reference to the other child node, in a binary tree
- Edge - The edge in a tree is the link between a parent and child node
- Leaf - A leaf is a node that does not have any children
- Height - The height of a tree is the number of edges from the root to the furthest leaf

- There are two categories of traversals when it comes to trees:

* Depth First
> Depth first traversal is where we prioritize going through the depth (height) of the tree first. There are multiple ways to carry out depth first traversal, and each method changes the order in which we search/print the root

- Pre-order: root >> left >> right   - > A, B, D, E, C, F
- In-order: left >> root >> right    - > D, B, E, A, F, C
- Post-order: left >> right >> root   -> D, E, B, F, C, A

 * Pre-order means that the root has to be looked at first.
 * When call preOrder for the first time, the root will be added to the call stack
 * tart reading our preOrder function’s code from top to bottom



* Breadth First
> Breadth first traversal iterates through the tree by going through each level of the tree node-by-node.uses a queue (instead of the call stack via recursion) to traverse the width/breadth of the tree. Let’s break down the process.

* putting the root into the queue, dequeue it and use that node in our code.
* From our dequeued node A, we can enqueue the left and right child (in that order).
* This leaves us with B as the new front of our queue. We can then repeat the process we did with A: Dequeue the front node, enqueue that node’s left and right nodes, and move to the next new front of the queue.
* reach a node that doesn’t have any children, we just dequeue it without any further enqueue


##### Binary Tree Vs K-ary Trees
- Binary Trees restrict the number of children to two (hence our left and right children).

-  K-ary Trees: Nodes are able have more than 2 child nodes

- Breadth First Traversal : still pushing nodes into a queue, but we are now moving down a list of children of length k, instead of checking for the presence of a left and a right child.


#### Binary Search Trees
> A Binary Search Tree (BST) is a type of tree that does have some structure attached to it. In a BST, nodes are organized in a manner where all values that are smaller than the root are placed to the left, and all values that are larger than the root are placed to the right.


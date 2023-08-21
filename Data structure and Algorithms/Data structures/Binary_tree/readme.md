### Binary Tree Part 1 Exercise

Add following methods to [BinarySearchTreeNode class](https://github.com/codebasics/data-structures-algorithms-python/blob/master/data_structures/8_Binary_Tree_1/binary_tree_part_1.py) created in main video tutorial

    1. find_min(): finds minimum element in entire binary tree
    2. find_max(): finds maximum element in entire binary tree
    3. calculate_sum(): calcualtes sum of all elements
    4. post_order_traversal(): performs post order traversal of a binary tree
    5. pre_order_traversal(): perofrms pre order traversal of a binary tree

### Binary Tree Part 2 Exercise

Modify delete method in class [BinarySearchTreeNode class](https://github.com/codebasics/data-structures-algorithms-python/blob/master/data_structures/9_Binary_Tree_2/binary_tree_part_2.py)
to use min element from left subtree. You will remove lines marked with ---> and use max value from left subtree

```
    def delete(self, val):
        if val < self.data:
            if self.left:
                self.left = self.left.delete(val)
        elif val > self.data:
            if self.right:
                self.right = self.right.delete(val)
        else:
            if self.left is None and self.right is None:
                return None
            elif self.left is None:
                return self.right
            elif self.right is None:
                return self.right

          --->  min_val = self.right.find_min()
          --->  self.data = min_val
          --->  self.right = self.right.delete(min_val)
```

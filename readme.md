# Binary trees

## Maximum depth leaf

Passed a binary tree, write a algorithm to calculate the maximum depth leaf.

### Example:

```
    3
   / \
  2   5
 /   / \
1   4   6
         \
          7
```

The output should be: 3

### Algorithm

This is a example implemented in java.

```java
public static int height(Node root) {
    if (root == null)
        return -1;

    int left = height(root.left);
    int right = height(root.right);

    if (left > right)
        return left + 1;

    return right + 1;
}
```

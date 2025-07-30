# Binary trees

## Insert algorithm

```java
public static Node insert(Node root, int data) {
    if (root == null) {
        return new Node(data);
    } else {
        Node cur;
        if (data <= root.data) {
            cur = insert(root.left, data);
            root.left = cur;
        } else {
            cur = insert(root.right, data);
            root.right = cur;
        }
        return root;
    }
}
```

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

# Dynamic Programming

### Balanced brackets

Example:

```py
def isBalanced(s):
    stack = []
    pair = {')': '(', '}': '{', ']': '['}
    for char in s:
        if char in pair.values():
            stack.append(char)
        elif char in pair:
            if not stack or stack[-1] != pair[char]:
                return "NO"
            stack.pop()
    return "YES" if not stack else "NO"
```

### Longest increasing subsequence

Example:

```py
nums = [10,9,10,12,13,15,11]

def length_of_lis(nums):
    lis = [1]*len(nums)
    answer = 1

    for i in range(len(nums)):
        for left in range(i):
            if nums[left] < nums[i]:
                if lis[left]+1 > lis[i]:
                    lis[i] = lis[left]+1
        answer = max(answer, lis[i])
    return answer

print(length_of_lis(nums))
```

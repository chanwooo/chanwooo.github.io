https://leetcode.com/problems/path-sum/



<details>
<summary markdown='span'>문제</summary>
<pre>
Given a binary tree and a sum, determine if the tree has a root-to-leaf path such that adding up all the values along the path equals the given sum.<br/>
Note: A leaf is a node with no children.<br/>
Example:<br/>
Given the below binary tree and sum = 22,<br/>
      5
     / \
    4   8
   /   / \
  11  13  4
 /  \      \
7    2      1
return true, as there exist a root-to-leaf path 5->4->11->2 which sum is 22.
</pre>
</details>




##### 입출력 예

| stdin                                            | stdout |
| ------------------------------------------------ | ------ |
| [5,4,8,11,null,13,4,7,2,null,null,null,1]<br/>22 | True   |

-----

5 - 4 - 11 - 2 의 경로를 따라갔을때 합은 22이다.

dfs를 이용해 leaf까지 탐색하여 원하는 값이 있는지 확인해야한다.

```python
class Solution:
    def dfs(self, node, total):
        if not node: 
            return

        total -= node.val

        if not node.left and not node.right and total == 0:
            self.ans = True
        self.dfs(node.left, total)
        self.dfs(node.right, total)
    
    def hasPathSum(self, root: TreeNode, sum: int) -> bool:
        self.ans = False
            
        self.dfs(root, sum)
        return self.ans
```



LeetCode에서 미리 구현해준 TreeNode를 내 로컬의 IDE에서 써보고싶었다.

다음과 같이 구현해둔것을 찾아서 같이 적어둔다.

```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

    def __repr__(self):
        return f"TreeNode({self.val}, {self.left}, {self.right})"
    
def insertLevelOrder(arr, root, i, n):
    # Base case for recursion
    if i < n:
        temp = TreeNode(arr[i])
        root = temp

        # insert left child
        root.left = insertLevelOrder(arr, root.left, 2 * i + 1, n)

        # insert right child
        root.right = insertLevelOrder(arr, root.right, 2 * i + 2, n)
    return root	

if __name__ == '__main__':
    arr = [5,4,8,11,None,13,4,7,2,None,None,None,1]
    n = len(arr)
    root = None
    root = insertLevelOrder(arr, root, 0, n)

```





참조

https://www.geeksforgeeks.org/construct-complete-binary-tree-given-array/

https://velog.io/@dadumvu/Leetcode-112.-Path-Sum
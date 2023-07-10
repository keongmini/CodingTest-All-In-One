# Recursion 재귀

자신을 정의할 때 자기 자신을 재참조하는 함수

시간 복잡도 - 재귀 함수 호출 수 n에 비례

# Tree 트리

서로 연결된 Node의 계층형 자료구조로써 root와 부모-자식 관계의 subtree로 구성되어 있음


## 이진트리


```python

class Node:
  def __init__(self, value = 0, left = None, right = None):
    self.value = value
    self.left = left
    self.right = right

class BinaryTree:
  def __init__(self):
    self.root = None

```

## 트리 순회
= 트리 탐색: 트리의 각 노드를 방문하는 과정 - 모든 노드를 방문해야 하기 때문에 완전 탐색
  - BFS
    ```python
    def bfs(root):
      visited = []
      if root is None:
        return 0;

      q = deque()
      q.append(root)
      while q:
        cur_node = q.popleft()
        visited.append(cur_node.value)

        if cur_node.left:
          q.append(cur_node.left)
        if cur_node.right:
          q.append(cur_node.right)

      reutrn visited
    ```
  - DFS
    - 전위순회 preorder (자식 노드에 가기 전에 자기 자신부터 방문)
    - 중위순회 inorder (left 자식 노드 먼저 방문 후 자기 자신 방문 후 right 노드 방문)
    - 후위순회 postorder (자식 노드 모두 방문 후 자기 자신 방문)
      ```python
      def postorder(root):
        if root is None:
          return

        left = postorder(root.left)
        right = postorder(root.right)
        print(root.value)

      postorder(root)
      ```

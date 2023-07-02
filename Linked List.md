# Linked List(연결 리스트)

Linked List: 노드라는 구조체가 연결되는 형식으로 데이터를 저장하는 자료구조
  - 메모리상에서 비연속적으로 저장되어 있지만 다음 노드의 메모리 주소값을 가리킴으로써 논리적으로 연속성으로 가짐
  - 메모리상에서 연속성을 유지하지 않아도 되기 때문에 메모리 사용이 좀 더 자유로움
  - 다음 노드의 주소값도 저장해야 하기 때문에 메모리 데이터 하나당 차지하는 메모리가 더 커짐


### Node

```python
class Node:
  def __init__(self, value = 0, next = None):
    self.value = value
    self.next = next

first = Node(1)
seconde = Node(2)
third = Node(3)

first.next = second
second.next = third
```


### Linked List

```python
class LinkedList(object):
  def __init__(self):
    self.head = None           # Linked List는 head가 있어야 함
```

#### Operations

1. append

시간복잡도 O(n)
   
```python
def append(self, value):
  new_node = Node(value)
  if not self.head:          # head가 첫번째 노드를 가리키도록
    self.head = new_node
  else:                      # next 노드 연결
    current = self.head
    while(current.next):     # next 노드가 없는 노드를 찾을 때까지 이동
      current = current.next
    current.next = new_node
```

2. get

시간복잡도 O(n)

```python
def get(self, idx):
  current = self.head
  for _ in range(idx):
    current = current.next
  return current.value
```

3. inset_at

4. remove_at

5. insert_back (tail 이용) - append와 비교

시간복잡도 O(1)

```python
class LinkedList(object):
  def __init__(self):
    self.head = None
    self.tail = None
  def append(self, value):
    new_node = Node(value)
    if not self.head:
      self.head = new_node
      self.tail = new_node
    else:
      self.tail.next = new_node
      self.tail = self.tail.next
```


* Linked List는 코테에 잘 나오지 않지만 트리나 다른 자료구조를 이해할 때 필요함



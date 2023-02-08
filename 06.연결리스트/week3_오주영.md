## 연결리스트 (Linked List) 한방향 VS 양방향
배열 : 연속된 메모리공간에 저장됨

연결리스트: 연결된 메모리공간에 저장되어 있는 것이 아니다
node: data(값), link (key, link)
마지막은 None(NULL)에 연결
가장 앞의 노드 : head node
2번째 노드의 값이 무엇이라고 물으면 상수시간안에 대답하지 못할 수 있다. 걸리는 시간이 노드의 위치에 따라 다르다

중간에 insert 5를 할 때 배열보다 연결리스트가 유리하다
연결리스트 삽입하고자 하는 곳의 앞뒤 노드에 대한 정보가 있다면 O(1)만큼의 시간이 걸린다.

양방향의 경우 양쪽 방향을 link가 되어있는 연결 리스트이다.
```py

class Node:
  def __init__(self, key=None):
    self.key = key
    self.next = None
  
  def __str__(self):
    return str(self.key) # 나중에 이 노드를 출력하고 싶을 때, print(v.key)말고 print(v.__str__)로 확인 가능

a = Node(3)
b = Node(9)
c = Node(-1)
a.next = b
b.next = c

```


개별적으로 만드는 경우 노드마다 이름을 만들어야 한다는 단점 존재
head노드만 알고 있어도 만들 수 있다.
head노드, 연결리스트에 있는 전체 사이즈를 통해 한방향 연결 리스트 객체 생성 가능



```
class SinglyLinkedList:
  def __init__(self): # 빈 리스트 생성
    self.head = None 
    self.size = 0
  
  + 삽입 methods
  + 삭제 methods
  + def __len__(self):
    return self.size

```

### 한방향 연결 리스트
#### 삽입연산 : pushFront, pushBack
head : L
size : 0

```py
class SinglyLinkedList:
  def __init__(self):
    self.head = None
    self.size = 0
  def pushFront(self, key):
    new_node = Node(key)
    new_node.next = L.head
    L.head = new_node
    L.size += 1

  def pushBack(self, key):
    v = Node(key)
    if len(self) == 0:
      self.head = v
    else:
      tail = self.head
      while tail.nex != None:
        tail = tail.next
      tail.next = v
    self.size += 1
```
#### 삭제연산 : popFront, popBack

지울때 지우고 싶은 노드가 있는지 여부 확인 필요
```py
def popFront(self):
  if len(self) == 0:
    return None
  else: # 하나 이상의 노드 존재
    x = self.head
    key = x.key
    self.head = x.next # head수정
    self.size -= 1 # size수정
    del x
    return key
```
tail노드를 지우고 싶으면 tail노드 앞의 prev노드의 prev.next = None, prev.next = tail.next하면 된다.
```py
def popBack(self):
  if len(self) == 0:
    return 0
  else:
    # running technique
    prev, tail = None, self.head
    while tail.next != None:
      prev = tail
      tail = tail.next
    if len(self) == 1:
      self.head = None
    else:
      prev.next = tail.next
    key = tail.key
    del tail
    self.size -= 1
    return key

```

pushFront, popFront  = O(1)
pushBack, popBack = O(n) # while 부분에서 많이 걸림

#### 한방향 연결리스트 : 탐색(search) + 제너레이터(generator)
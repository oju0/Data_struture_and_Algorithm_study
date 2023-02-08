
## Queue
FIFO(First In Firts out) 규칙의 순차적 자료구조
stack: 말미잘
queue: th
|      | stack | queue|
|-----|-----|-----|
|insert| push | enqeue|
|delete| pop |deqeue|
스택의 가장 마지막만 알면 되지만 큐는 2개의 인덱스가 필요ㅗ
어디가 dequeue되고 어디가 enqueue되는지

front: first_index(저장된 원소 중 첫번째 원소)
rear : last_index(저장된 원소 중 마지막 번째 원소)

```py
class Queue:
  def __init__(self):
    self.items = [] # 빈 리스트
    self.front_index = 0
  
  def enqueue(self, val):
    self.items.append(val)

  def dequeue(self):
    if self.front_index = len(self.items):
      print("Q is empty")
      return None
    else:
      x = self.items[front_index]
      self.front_index +=1
      return x

```

ex) Josephus Problem
n = 6, k = 2 -> 5
원형으로 선 후 2번째 사람마다 죽는 것, 마지막까지 남은 사람이 최종 승장
Josephus(n, k):
  return 최종 생존자의 번호

```
1 2 3 4 5 6 7 8 9

Q에서 k-1인 2개를 dequeue하자마자 맨뒤에 enqueue
K번째 값은 dequeue만 한다
반복
Q에 1개의 값만 남을 때 까지
```

stack + queue = dequeue
양쪽 끝으로 다 들어갈 수 있고 나올 수 있다
appendleft, popleft, pop, append
```py
python - dequeue class
```

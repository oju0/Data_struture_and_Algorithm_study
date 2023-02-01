# Python + 자료구조

## 목차

1.  자료구조와 알고리즘 : 가상머신, 언어, 코드, 알고리즘/자료구조 복잡도, Big-O기호
2.  Array(List), Stack, Queue, Dequeue
3.  Linked List(한방향, 양방향)
4.  Hash Table : 해시 함수, 해시 충돌 해결 방법
5.  Tree
    - priority Queue : Heap + HeapSort
    - 이진트리 : 순회
    - 이진탐색트리 : 삽입 삭제 등
    - 균형이진탐색트리 : AVL, 2-3-4, Red-Block, Splay
6.  Graph
    - 표현법, 순회법(DFS, BFS)
    - 최단 경로 알고리즘(Bellman-Ford, Dijkstra algorithms)

---

# 자료구조(DataStructure), 알고리즘(Algorithm)

자료구조 : 자료를 담는 구조

### 자료(data) -> 저장 공간(memory)이 있어야 하고 + 읽기, 쓰기, 삽입, 삭제, 탐색이 가능해야(연산)

입력 데이터를 기반으로 논리적으로 문제를 해결하는 것이 알고리즘

알고리즘 : 자료구조의 유한한 횟수의 연산들을 통해 정답을 출력하는 것  
자료구조의 예

변수(variable)

```
a = 5 <- 쓰기 연산, 변수 print(a) <- 읽기 연산, 이름
```

배열(array), 리스트(list)

```
A = [3, -1, 5, 7]
각 원소의 index를 통해 값에 접근 읽기 쓰기
A[3]
삽입 : A.append(9), A.insert
삭제 : A.pop()
```

### 인류 최초의 알고리즘 : 최대공약수(GCD) 계산 알고리즘 (By Euclid)

ac.페르시아, Algebra수학자 Al-Kharizmi -> Algorismus + Arithmos -> Algorithm

- gcd(8, 12) = max{1, 2, 4} = 4  
  gcd(8, 12) -> gcd(8, 4) -> ... -> 한쪽이 0이 되면 남은 막대기의 길이가 gcd이다
- python

```
def gcd(a, b): while (a != 0 and b != 0): if a > b: a -= b else: b -= a return a + b
```

gcd(2, 100) -> 빼는 방식으로 구하는 경우 50번 반복

다른 방법이 없을까?

gcd_sub(빼기), gcd_mod(나머지), gcd_rec(재귀)

```
def gcd_mod(a, b):
  while (a * b != 0):
    if a > b:
        a %= b
    else:
        b %= a
```

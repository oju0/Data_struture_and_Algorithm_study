# 2주차 순차적 자료구조 : 배열과 리스트

## 배열(array) VS 리스트(list) python
가장 기본적인 순차적인(sequential) 자료구조

Python
```
A.append
A.pop
A.insert
A.remove
A.indexx
A.count

```

#### 리스트 : 용량 자동조절 (danamic array)
C언어 같은 경우 직접 용량 조절을 해야 한다

```c
int A[4] = {2, 4, 0, 5};
A[4] = 10; <- Error
B = (int *)malloc(6 * 4) : 정수가 4바이트
B 2, 4, 0, 5, , ,
A = B

```

Python의 경우
```python
import sys
A = [] # 빈 리스트
print(sys.getsizeof(A)) # 28 bytes
A.append(18) # A = [10]
print(Sys.getsizeof(A))
```

list class
```py
A
capacity: 용량 100 (2)
n : 현재 저장된 값의 개수 (0)

A.append(x):
  if A.n < A.capacity:
    A[n] = x
    A.n = n + 1
  else:
    B = A.capacity * 2 # 크기의 리스트 새로 할당
    for i in range(n):
      B[i] = A[i] #O(n)
  del A 
  A = B
  A[n] = x
  A.n = n + 1
```

- A.append, A.po: O(1) 평균
- A.insert, A.remove : O(n) w.c
- A.index, A.count : O(n) w.c
- A.pop() : O(1) 평균
- A.pop(k) : O(n) w.c

## 순차적 자료구조(sequential data structures) 소개
### 1. 배열, 리스트
index로 임의의 원소를 접근
연산자 [] A[2]= -1 (O(1))
삽입(append, insert)
삭제(pop, remove)
어느 위치에 삽입, 삭제하는지에 따라 O(1) 또는 O(n)의 시간복잡도를 가진다

### 2. stackm queue dequeue
제한된 접근(삽입, 사젝)만 허용
#### stack : LIFO(Last In First Out) / 말미잘
push
pop
#### queue : FIFO(First in First Out) / 사람
선착순
#### dqueue : stack + queue
스택과 큐의 삽입, 삭제연산 가능

### 3. linked list(연결 리스트)
연속되지 않은 메모리공간에 독립적으로 저장되어 있는데 다음값이 어디에 있는지에 대한 주소를 저장하고 있는 구조
마지막에 다음에 값이 없음을 표시
C : Null
Python : none
인덱스로 접근 X

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

---

## Stack
삽입, 삭제, 탐색을 자료구조는 제공해야 한다
```
삽입 : push 삭제 : pop 
top 맨 위의 값
len 스택의 값의 개수
---------------------------------------------
리스트 append      pop = 리스트는 더 다양한 요소가 많다
```

```python
class Stack:
  def __init__(self): # 생성함수 # self  생성된 객체
    self.items = [] # 빈 리스트
  
  def push(self, val): # O(1)
    self.items.append(val)

  def pop(self): # O(1)
    try:
      return self.items.pop() # pop할 아이템이 없으면
    except IndexError:
      print("Stack is empty")

  def top(self):  # O(1)
    try:
      return self.items[-1]
    except IndexError:
      print("Stack is empty")
  
  def __len__(self): # len()로 호출하면 stack의 item 수 반환,  # O(1)
    return len(self.items) # len(S)
  
```

예) 괄호 맞추기
(2 + 5) * 7 - ((3 - 1) / 2 + 7)
(()()) (())(
문제
입력 : 왼쪽, 오른쪽 괄호의 문자열
출력 : 괄호쌍이 맞춰져 있으면 True, 아니면 False
관찰
.... ( .... ) ....
```py
for p in parseq:
  if p == '(': S.push(p)
  elif p == ')' : S.pop() # 에러 : 오른쪽이 더 많음
  else: print("Not allowed Symbol")
if len(S) > 0: return False #왼쪽이 더 많은
else: return True 
```

스택 예 2: 계산기 코드 작성
"2 + 3 * 5" -> 피연산자(operand), 연산자(operator) : 토큰(Token) -> )2 + (3 * 5)) -> 17출력
이항연산자(binary operator) 2 + 3 3 *5
단항연산자(unary operator) +3 -6
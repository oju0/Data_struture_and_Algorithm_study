
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
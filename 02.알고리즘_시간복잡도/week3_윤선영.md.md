# Week3_알고리즘 시간복잡도

## <자료구조와 알고리즘 성능1>

![](C:\Users\multicampus\AppData\Roaming\marktext\images\2023-02-15-19-32-12-image.png)

- 자료구조 + 알고리즘 : 코드(C, java, Python)를 이용해 컴퓨터로 구현
  
  - HW/SW 환경이 상이하고, 다양한 크기의 입력이 존재한다는 문제 有

- 하드웨어와 소프트웨어 환경에 구애 받지 않는 가상의 환경 가정!

- **가상 컴퓨터(Virtual Machine) + 가상 언어(Psuedo Language) + 가상 코드(Psuedo Code)** : HW/SW 환경에 독립적이어서 누구나 똑같은 환경에서 코드를 작성할 수 있다!

### 가상컴퓨터

- 튜링머신 -> Von Neumann의 RAM(Random Access Machine) 모델

- RAM = CPU + Memory + 기본연산(단위 시간에 수행되는 연산들)

- 기본연산 : 아래와 같은 기본 연산을 1단위시간 내에 수행할 수 있는 가상 컴퓨터 환경을 RAM 모델이라고 한다!
  
  - 배정, 대입, 복사연산 : A = B (읽고 쓴다)
  
  - 산술연산 : +, -, *, /
  
  - 비교연산 : >, >=, <, <=, ==, !=
  
  - 논리연산 : AND, OR, NOT
  
  - 비트연산: bit-AND/OR/NOT

### 가상언어 (Psuedo/Virtual Language)

![](C:\Users\multicampus\AppData\Roaming\marktext\images\2023-02-15-19-39-24-image.png)

- 배정, 산술, 비교, 논리, bit-논리같은 기본연산을 표현할 수 있으면 된다.

- 비교  : if, if else, if... elseif(elif) ... else 를 표현할 수 있어야 한다.

- 반복 : for, while 을 표현할 수 있어야 한다. 

- 함수 : 정의, 호출, return 할 수 있어야 한다.

- 위와 같은 기능을 수행할 수 있는 문법을 제공하면 가상언어라고 할 수 있다. 

### 가상코드 (Psuedo Code)

- 가상언어를 사용해서 코드를 작성하면 가상코드가 된다.

- 실제로 동작하지 않아도 괜찮음!!

- 예시

![](C:\Users\multicampus\AppData\Roaming\marktext\images\2023-02-15-19-39-59-image.png)

- 예시에 대해 구체적인 입력을 생각해본다면?

![](C:\Users\multicampus\AppData\Roaming\marktext\images\2023-02-15-19-41-42-image.png)

- but 무한히 많은 input값이 존재하기 때문에, 기본연산이 몇회나 일어나는지 정확히 알기 힘들다! A의 input size에 따라 몇번의 연산이 수행되는지는 계속해서 달라짐! 
  
  ![](C:\Users\multicampus\AppData\Roaming\marktext\images\2023-02-15-19-45-09-image.png)

### <mark>알고리즘 수행시간 = 최악의 입력에 대한 기본연산 횟수</mark>

- 예시의 경우 A 배열이 [2, 5, 7, 9, 15, 26] 같은 오름차순일 때가 최악의 케이스!
  
  - 2n-1번의 기본연산을 수행한다!
  
  ![](C:\Users\multicampus\AppData\Roaming\marktext\images\2023-02-15-19-51-31-image.png)

#### 예시 1) n에 비례해서 수행시간 변화

![](C:\Users\multicampus\AppData\Roaming\marktext\images\2023-02-15-19-53-40-image.png)

#### 예시 2) n의 제곱에 비례해서 수행시간 변화

![](C:\Users\multicampus\AppData\Roaming\marktext\images\2023-02-15-19-55-29-image.png)

![](C:\Users\multicampus\AppData\Roaming\marktext\images\2023-02-15-19-57-19-image.png)

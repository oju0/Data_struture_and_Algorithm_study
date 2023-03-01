# 힙

Heap : 힙 성질을 만족하는 **이진트리**

H[k]의 왼쪽 자식노드 : H[2 * k + 1]
H[k]의 오른쪽 자식노드 : H[2 * (k + 1)]
H[k]의 부모노드 : H[(k - 1) // 2]

상수 시간의 연산으로 왼쪽, 오른쪽, 부모 노드를 계산할 수 있다는 장점이 있다.
단점은 메모리 낭비가 있다.
레벨을 꽉꽉차있는 형태의 이진트리이면 메모리를 아낄 수 있다.

**힙 성질 : 모든 부모노드의 키값은 자식 노드의 키값보다 작지 않다.**

루트노드 : 가장 큰 값
make heap
제공 연산
1. Insert
2. find_max : return A[0] 
3. delete_max

## make_heap : heapify-down
```
make_heap(A):
  n = len(A)
  for k in range(n-1, -1, -1):
    # A[k] => heap 성질 만족하는 곳으로
    heapify_down(k, n)
```
-> O(n * t) = O(nh)

```
heapify-down(k,n)
  # A[k], n값
  while A[k] != leaf node:
    L, R = 2 * k + 1, 2 * k + 2
    m = index max(A[k], A[L], A[R])
    if k != m:
      A[k]<-> A[m]
      k = m
    else:
      break
```
-> O(h) 힙의 높이

n개 노드 : 힙의 높이 h
1 + 2 + 2^2 + 2^3 + ... + 2^(h-1) + 1 <= n
2^h <= n
아무리 커도 h <= log2(n)

heapifydown : O(h) = O(logn)
makeheap : O(nh) = O(nlogn) -> O(n)까지도 갈 수 있다
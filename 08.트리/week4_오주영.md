# 트리

지금까지는 순차적 자료구조에 대해 알아보았다.
순차적 자료구조 : 배열 - 인덱스, 연결리스트 - 링크(next, prev)
부모 -> 자식간의 관계 : 연결리스트는 트리의 특별한 구조라고 볼 수 있다.

트리, 이진트리(binary tree) - 가장 간단하면서도 자주 사용됨

루트(root)
노드(node)
링크(link, edge)
리프(leaf)
레벨(level)
경로(path), 경로의 길이(path length, 엣지 개수)
부모노드, 형제노드, 자식노드

표현법 1: 리스트 : level0 -> level1 -> level2 -> ...
A = [a, b, c, None, d, e, f]

표현법 2: 리스트안에 리스트
[a, [a의 왼쪽부트리], [a의 오른쪽부트리]]

표현법 3: node class 생성, key와 자식로드 가지는 left, right라는 이름으로 link필요
key, left, right, parent표현할 수 있는 4가지는 필수적


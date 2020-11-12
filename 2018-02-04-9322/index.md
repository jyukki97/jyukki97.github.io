# 9322 철벽 보안 알고리즘

[https://www.acmicpc.net/problem/9322](http://www.acmicpc.net/problem/9322)

#### **풀이:**
1. 제 1 공개키에 각각에 단어들이 제 2 공개키에 어디에 있는지 확인한다.
2. 제 1 공개키에 첫번째 단어부터 제 2 공개키에서의 위치에 있는 암호키를 출력한다.

#### **코드:**
사용언어 : Python 3
```
a,b,c=[],[],[]
for i in range(int(input())):
    n=int(input())
    a,b,c=input().split(),input().split(),input().split()
    for t in range(n):
        print(c[b.index(a[t])],end=" ")
```

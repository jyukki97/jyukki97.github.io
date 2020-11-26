# 9550 아이들은 사탕을 좋아해

[https://www.acmicpc.net/problem/9550](http://www.acmicpc.net/problem/9550)

#### **풀이:**
1. 사탕개수를 최소 K개 만큼 주어야 하므로 각각의 사탕을 K로 나눈 몫을 모두 더한 값을 출력한다.

#### **코드:**
사용언어 : Python 3
```
T = int(input())
for i in range(T):
    cnt = 0    
    n,k = map(int,input().split(' '))
    c = input().split(' ')
    for t in range(n):
        cnt += int(c[t]) // k
    print(cnt)
```

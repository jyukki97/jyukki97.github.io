# 10808 알파벳 개수

[https://www.acmicpc.net/problem/10808](http://www.acmicpc.net/problem/10808)

#### **풀이:**
1. 알파벳 순서대로 나온 카운트를 계산하여 하나씩 출력

#### **코드:**
사용언어 : Python 3
```
n=input()
for i in range(97,123):
    print(n.count(chr(i)),end=' ')
```

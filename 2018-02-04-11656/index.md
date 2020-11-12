# 11656 접미사 배열

[https://www.acmicpc.net/problem/11656](http://www.acmicpc.net/problem/11656)

#### **풀이:**
1. 접미사를 모두 리스트에 넣는다.
2. 리스트를 사전순으로 정렬하고 출력한다.

#### **코드:**
사용언어 : Python 3
```
n=input()
l=[]
for i in range(len(n)):
    l.append(n[i:])
l.sort()
for i in range(len(n)):
    print(l[i])
```

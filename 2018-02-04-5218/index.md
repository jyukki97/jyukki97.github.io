# 5218 알파벳 거리

[https://www.acmicpc.net/problem/5218](http://www.acmicpc.net/problem/5218)

#### **풀이:**
1. 알파벳 거리를 출력
2. 만약 음수라면 26을 더한다.

#### **코드:**
사용언어 : Python 3
```
n=int(input())
for i in range(n):
    a,b=map(str,input().split())
    print("Distances:",end=' ')
    for t in range(len(a)):
        if(ord(a[t])>ord(b[t])):
            print(ord(b[t])-ord(a[t])+26,end=' ')
        else:
            print(ord(b[t])-ord(a[t]),end=' ')
    print()
```

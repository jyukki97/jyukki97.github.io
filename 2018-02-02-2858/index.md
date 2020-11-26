# 2858 기숙사 바닥

[https://www.acmicpc.net/problem/2858](http://www.acmicpc.net/problem/2858)

#### **풀이:**
1. 전체 사각형의 면적으로 가로 세로를 찾은 후
2. 그 가로 세로에서 2를 뺀것의 넓이가 안쪽 갈색의 면적과 같다면
3. 그 가로 세로가 각각 L, W 라고 할 수 있다.

#### **코드:**
사용언어 : Python 3
```
r,b=map(int,input().split())
for i in range(3,(r+b)//2):
    if((r+b)%i==0 and (i-2)*(((r+b)/i)-2)==b):
        print(((r+b)//i),i)
        break
```

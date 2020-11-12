# 1357 뒤집힌 덧셈

[https://www.acmicpc.net/problem/1357](http://www.acmicpc.net/problem/1357)

#### **풀이:**
1. 두 숫자를 뒤집어서 입력을 받는다.
2. 입력받은 두 숫자를 더한 후 다시 뒤집는다.

#### **코드:**
사용언어 : Python 3
```
x,y=map(int,input()[::-1].split())
print(int(str(x+y)[::-1]))```

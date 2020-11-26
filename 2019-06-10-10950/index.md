# [백준]10950 A+B - 3

[https://www.acmicpc.net/problem/10950](http://www.acmicpc.net/problem/10950)

#### **풀이:**
1. 반복 횟수를 입력받은 후 입력받은 두 수의 합을 출력

#### **코드:**
사용언어 : Python 3
```{.python}
for i in range(int(input())):
    print(sum(map(int,input().split())))
```

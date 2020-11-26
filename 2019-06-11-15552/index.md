# [백준]15552 빠른 A+B

[https://www.acmicpc.net/problem/15552](http://www.acmicpc.net/problem/15552)

#### **풀이:**
1. 반복 횟수를 입력받은 후 입력받은 두 수의 합을 출력
2. 간단한 문제이지만 매우 많은 테스트케이스의 수가 있으므로 input() 대신 sys.stdin().readline()을 사용한다.

#### **코드:**
사용언어 : Python 3
```{.python}
import sys
for i in range(int(input())):
    print(sum(map(int,sys.stdin.readline().split())))
```

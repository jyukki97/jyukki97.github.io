# [백준]1850 최대공약수

[https://www.acmicpc.net/problem/1850](http://www.acmicpc.net/problem/1850)

# **풀이:**
1. 두 수를 입력받는다
2. 두 수의 최대공약수를 구한다.
3. 최대공약수만큼 1을 반복해서 출력한다.

# **코드:**
사용언어 : Python 3
```python
a,b=map(int,input().split())
while b: a,b=b,a%b
print('1'*a)
```

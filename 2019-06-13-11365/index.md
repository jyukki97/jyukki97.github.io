# [백준]11365 !밀비 급일


[https://www.acmicpc.net/problem/11365](http://www.acmicpc.net/problem/11365)

# **풀이:**
1. 문자열을 입력받고, 그 문자열을 뒤집어서 출력한다.
2. 문자열이 END라면 반복을 중지한다.

# **코드:**
사용언어 : Python 3
```python
while 1:
 a=input()
 if a=='END':break
 print(a[::-1])
```

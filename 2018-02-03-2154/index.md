# [백준]2154 수 이어 쓰기 3


[https://www.acmicpc.net/problem/2154](http://www.acmicpc.net/problem/2154)

# **풀이:**
1. 전체 수를 string타입으로 나열한다.
2. 그 숫자 중 제시된 숫자 n이 맨 처음으로 나오는 인덱스를 출력한다.

# **코드:**
사용언어 : Python 3
```python
n,s=int(input()),""
for i in range(1,n+1):
    s+=str(i)
print(s.find(str(n))+1)
```

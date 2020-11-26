# [백준]1712 손익분기점


[https://www.acmicpc.net/problem/1712](http://www.acmicpc.net/problem/1712)

# **풀이:**
1. 고정비용을 노트북 가격에서 생산비인 가변 비용을 뺀 값으로 나눈 몫을 출력한다.
2. 만약 가변비용이 노트북의 가격보다 높다면 -1을 출력한다.


# **코드:**
사용언어 : Python 3
```python
a,b,c=map(int,input().split())
if b>=c:
    print("-1")
else:
    print(a//(c-b)+1)
```

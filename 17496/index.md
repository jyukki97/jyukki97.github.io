# [백준]17496 스타후르츠


https://www.acmicpc.net/problem/17496

# 풀이:

((여름의 일 수 - 1) / 스타후르츠가 자라는데 걸리는 일 수) *  스타후르츠를 심을 수 있는 칸의 수 * 스타후르츠 개당 가격 

여름의 일 수에서 1을 빼주는 이유는 마지막 날에는 스타후르츠를 수확할 수 없기 때문에!!



# **코드:** 

사용언어 :  python

```python
a,b,c,d=map(int,input().split())
print((a-1)//b*c*d)
```

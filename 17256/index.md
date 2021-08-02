# [백준]17256 달달함이 넘쳐흘러


https://www.acmicpc.net/problem/17256

# 풀이:

차례대로 c.x - a.z, c.y / a.y, c.z - a.x 를 출력한다.



# **코드:** 

사용언어 :  python

```python
x,y,z=map(int,input().split())
q,w,e=map(int,input().split())
print(q-z,w//y,e-x)
```


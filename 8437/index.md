# [백준]8437 Julka


https://www.acmicpc.net/problem/8437

# 풀이:

처음 값이 a + b

두번째 값이 a - b 이므로

a = (처음 값 + 두번째 값) / 2

b = (처음 값 - 두번째 값) / 2

이다.



# **코드:** 

사용언어 :  python

```python
a,b=map(int,open(0))
c=(a+b)//2
print(c,a-c)
```


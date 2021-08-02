# [백준]11283 한글 2


https://www.acmicpc.net/problem/11283

# 풀이:

한글을 유니코드 값으로 변환시켜주는 ord() 함수를 사용하여 푼다.

'가'의 값이 44032이므로 값에 44031을 뺀 값을 출력해준다.



# **코드:** 

사용언어 :  python

```python
print(ord(input())-44031)
```


# [백준]1919 애너그램 만들기


[https://www.acmicpc.net/problem/1919](http://www.acmicpc.net/problem/1919)

# **풀이:**
1. a~z까지의 알파벳 중 문자열에 나온 개수를 확인 후 그 차이를 출력한다.

# **코드:**
사용언어 : Python 3
```python
a,b=input(),input()
print(sum(abs(b.count(chr(i))-a.count(chr(i)))for i in range(97,123)))
```

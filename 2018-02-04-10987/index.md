# 10987 모음의 개수

[https://www.acmicpc.net/problem/10987](http://www.acmicpc.net/problem/10987)

#### **풀이:**
1. 모음의 개수를 출력

#### **코드:**
사용언어 : Python 3
```
n=input()
print(sum(n.count(i)for i in 'aeiou'))
```

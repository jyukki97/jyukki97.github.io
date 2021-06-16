# [백준]1089 스타트링크 타워


https://www.acmicpc.net/problem/12787

# 풀이:

5 * 3 자리에서 각 자리에 '#' 이 들어올 경우 될 수 없는 숫자를 찾아놓는다.

ex) (0, 0) 자리에 '#' 이 올 경우 1은 절대 될 수 없다.





첫 번 째 숫자 부터 N까지의 숫자를 찾아가면서 가능한 숫자를 저장해놓는다.





가능한 숫자를 모두 조합한다면, 너무 많은 조합이 가능하므로 다른 방법을 사용한다.





ex) 각 자리에 [1], [2, 3], [1, 8, 9] 가 가능하다면, 만들 수 있는 조합은

121, 128, 129, 131, 138, 139 로 총 6가지 이다. 

이것을 100 * 1 * (2 * 3) + 10 * (2 + 3) * (3 * 1) + 1 * (1 + 8 + 9) * (1 * 2) 로 계산한다면 쉽게 계산할 수 있다.  



# **코드:** 

사용언어 :  python

```python
a, b = input(), []
for i in range(5):
    b.append(input())

num = [
    [[1], [1, 4], []],
    [[1,2,3,7], [0,1,2,3,4,5,6,7,8,9], [5, 6]],
    [[1, 7], [0, 1, 7], []],
    [[1, 3,4,5,7,9], [0,1,2,3,4,5,6,7,8,9], [2]],
    [[1, 4, 7], [1,4,7], []]]

q = []
for i in range(int(a)):
    v = [False for i in range(10)]
    for t in range(5):
        for y in range(3):
            if b[t][i*4+y] == '#':
                for e in num[t][y]:
                    v[e] = True
    w = []
    for e in range(10):
        if v[e] == False:
            w.append(e)
    q.append(w)
s = 1
for i in q:
    s *= len(i)

if s == 0:
    print(-1)
else:
    result = 0

    for key, i in enumerate(q):
        result += sum(i) * (10 ** (len(q) - key - 1)) * (s / len(i))

    print(round(result / s, 5))
```

# [백준]1092 배


https://www.acmicpc.net/problem/1092

# 풀이:

크레인과 박스를 정렬한다

단, 이때 정렬은 내림차순으로 해야한다. 오름차순으로 할 경우 안되는 경우의 수가 존재.   



정렬된 크레인과 박스의 맨 처음을 비교한다. 만약 박스의 무게가 더 크다면, 모든 박스를 옮길 수 없으므로 -1을 출력한다.  



크레인을 한칸씩 오른쪽으로 이동시키면서 박스를 확인한다. 옮긴 박스는 0으로 바꾸고, 이미 0인 박스는 지나친다. 

모든 크레인을 사용했다면 time을 1늘리고, 다시 반복한다.

모든 박스를 옮길 때까지 반복한 후 time을 출력한다.



# **코드:** 

사용언어 :  python

```python
a,b,c,d=int(input()),list(map(int, input().split())),int(input()),list(map(int, input().split()))
b.sort(reverse=True)
d.sort(reverse=True)
if b[0] < d[0]:
    print(-1)
else:
    p, t = [0] * a, 0
    while c:
        for i in range(a):
            while p[i] < len(d):
                if d[p[i]] and b[i] >= d[p[i]]:
                    d[p[i]] = 0
                    p[i] += 1
                    c -= 1
                    break
                p[i] += 1
        t += 1
    print(t)
```

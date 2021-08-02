# [백준]2845 파티가 끝나고 난 뒤


https://www.acmicpc.net/problem/2845

# 풀이:

상근이가 계산한 참가자의 수 -> L * P 와 각 기사에 적혀있는 참가자의 수의 차이를 출력한다



# **코드:** 

사용언어 :  python

```python
l,p=map(int,input().split())
for i in [*map(int,input().split())]: print(i-l*p,end=' ')
```


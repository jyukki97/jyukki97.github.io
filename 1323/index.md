# [백준]1323 숫자 연결하기


https://www.acmicpc.net/problem/1323

# 풀이:

나머지 연산의 성질을 이용한다.

나머지 연산의 경우 연산에 어디에 나머지 연산을 추가하든 나머지 연산의 값만 동일하다면, 최종 값도 동일하게 나온다.

그러므로 주어진 N을 K로 나눈 나머지를 확인하고,

0이 아니라면, 나온 나머지를 N과 연결하여 다시 K로 나눈 나머지를 확인한다.

0이 나올 때까지 반복한다.

나머지 연산 특성상 일정 개수 이상일 경우 반복하기 때문에 무한루프에 빠질 수 있다. 그러므로 최대 K번을 넘기지 않는다.





# **코드:** 

사용언어 :  python

```python
n,k=map(int,input().split())
b,c,l=n,-2,pow(10,len(str(n)))
for i in range(k):
    b%=k
    if not b:c=i;break
    b=b*l+n
print(c+1)
```

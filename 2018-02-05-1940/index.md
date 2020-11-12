# 1940 주몽

[https://www.acmicpc.net/problem/1940](http://www.acmicpc.net/problem/1940)

#### **풀이:**
1. 재료들이 가진 고유의 번호를 가진 리스트를 a라고 하자
2. 이 때 갑옷을 만드는데 필요한 숫자인 M에서 i번째 고유번호인 a[i]를 뺀 값이
3. 리스트 a에 있다면 갑옷을 1개 만들 수 있는 것이므로 카운트를 1 증가시킨다.
4. 계속 증가시키다 보면 서로 짝이되는 수 2개를 모두 카운트를 시키게 되므로 2로 나눠준다.

#### **코드:**
사용언어 : Python 3
```
n,m=int(input()),int(input())
a=input().split()
print(sum(a.count(str(m-int(a[i])))for i in range(n))//2)
```

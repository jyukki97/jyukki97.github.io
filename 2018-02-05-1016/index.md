# 1016 제곱 ㄴㄴ 수

[https://www.acmicpc.net/problem/1016](http://www.acmicpc.net/problem/1016)

#### **풀이:**
1. min 수 부터 max 까지 제곱수의 배수가 되는 수를 찾는다.
2. max-min+1 에서 위에서 찾은 제곱수의 배수의 개수를 뺀다.

#### **코드:**
사용언어 : Python 3
```
n,m=map(int,input().split())
a,b=0,[0]*1000001
for i in range(2,int(m**.5)+1):
    q=n
    if n%(i*i)!=0:
        q=(n//(i*i)+1)*i*i
    for t in range(q,m+1,i*i):
        if b[t-n]==0:
            b[t-n]=1
            a+=1
print(m-n+1-a)
```

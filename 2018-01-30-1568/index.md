# 1568 새

[https://www.acmicpc.net/problem/1568](http://www.acmicpc.net/problem/1568)

#### **풀이:**
1. 처음 새의 수 n에서 숫자 k를 노래할 때 나중 새의 수 = n - k
2. 노래의 숫자 수를 1씩 증가시켜가며 새의 수보다 많아질 경우 1로 돌아간다.
3. 만약 새의 수가 0이되면 카운트를 출력한다.

#### **코드:**
사용언어 : Python 3
```
k=int(input())
cnt,s=0,1
while True:
    if k==0:
        break
    if s>k:
        s=1
    cnt+=1
    k-=s
    s+=1
print(cnt)
```

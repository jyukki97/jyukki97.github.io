# 1302 베스트셀러

[https://www.acmicpc.net/problem/1302](http://www.acmicpc.net/problem/1302)

#### **풀이:**
1. 문자열을 하루 동안 팔린 책의 개수 N만큼 받아드린다.
2. 책 제목이 같을경우 책의 개수를 1씩 증가시킨다.
3. 팔린 책의 개수가 가장 많은 책을 출력한다.
4. 만약 팔린 책의 개수가 같다면 사전순으로 먼저 나오는 것을 출력한다.

#### **코드:**
사용언어 : Python 3
```
n=int(input())
s={}
q=''
w=0
for i in range(n):
    k=input()
    if(k in s):
        s[k]+=1
    else:
        s[k]=1
    if(s[k]>w):
        w=s[k]
        q=k
    elif(s[k]==w):
        if(q>k):
            q=k
print(q)
```

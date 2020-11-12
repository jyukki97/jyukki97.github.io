# 2896 무알콜 칵테일

[https://www.acmicpc.net/problem/2896](http://www.acmicpc.net/problem/2896)

#### **풀이:**
1. 주스의 비율을 주스의 양으로 나눈 값이 가장 작은 주스를 찾는다.
2. 주스의 비율에서 주스의 양 * 1번에서 구한 값 을 출력한다.
 

#### **코드:**
사용언어 : Python 3
```
a,b,c=map(int,input().split())
d,e,f=map(int,input().split())
g=min(a/d,b/e,c/f)
print("%.4f %.4f %.4f"%(a-d*g,b-e*g,c-f*g))
```

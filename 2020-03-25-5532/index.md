# [백준]5532 방학 숙제

https://www.acmicpc.net/problem/5532

# 풀이:

국어를 풀어야 하는 날짜와 수학을 풀어야 하는 날짜를 각각 a, b라고 했을 때,

a, b 중 더 높은 값을 방학일에서 뺀다면, 놀 수 있는 날의 최댓값이 된다.



# **코드:** 

사용언어 : c
```c++
main(n,a,b,c,d){
    scanf("%d%d%d%d%d",&n,&a,&b,&c,&d);
    a=a/c+(a%c?1:0),b=b/d+(b%d?1:0);
    printf("%d",n-(a<b?b:a));
}
```


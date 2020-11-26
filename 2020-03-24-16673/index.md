# [백준]16673 고려대학교에는 공식 와인이 있다

https://www.acmicpc.net/problem/16673

# 풀이:

ΣKn + ΣPn^2 (1 ~ C)

Kn(n+1)/2 + Pn(n+1)(2n+1)/6

n(n+1)(3K+P(2n+1))/6



# **코드:** 

사용언어 : c
```c++
main(c,k,p){
    scanf("%d%d%d",&c,&k,&p);
    printf("%d",((c*c+c)*(3*k+p*2*c+p))/6);
}
```


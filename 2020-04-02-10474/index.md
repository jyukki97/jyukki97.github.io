# [백준]10474 분수좋아해?

https://www.acmicpc.net/problem/10474

# 풀이:

(a / b) (a %b) / (b) 를 순서대로 출력해준다.



# **코드:** 

사용언어 : c	
```c++
main(a,b){
    for(;scanf("%d%d",&a,&b)*a*b;)
        printf("%d %d / %d\n",a/b,a%b,b);
}
```


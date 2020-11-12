# [백준]16486 운동장 한 바퀴

https://www.acmicpc.net/problem/16486

# 풀이:

원 둘레 + 직사각형 가로길이 * 2



# **코드:** 

사용언어 : c
```c++
main(n,m){
    scanf("%d%d",&n,&m);
    printf("%f",2*(n+m*3.141592));
}
```


# [백준]14656 조교는 새디스트야!!

https://www.acmicpc.net/problem/14656

# 풀이:

현재의 줄번호와 학생의 번호가 다르다면 +1 해준다.



# **코드:** 

사용언어 : c	
```c++
i,c;
main(a){
    for(gets(&a);~scanf("%d",&a);)
        c+=a!=++i;
    printf("%d",c);
}
```


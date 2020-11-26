# [백준]2083 럭비 클럽

https://www.acmicpc.net/problem/2083

# 풀이:

나이가 17세보다 많거나, 몸무게가 80kg 이상이면, 'Senior'

아니라면 'Junior'를 출력한다.



# **코드:** 

사용언어 : c
```c++
char c[11];
main(a,b){
    for(;scanf("%s%d%d",c,&a,&b)*a;)
        printf("%s %s\n",c,a>17||b>=80?"Senior":"Junior");
}
```


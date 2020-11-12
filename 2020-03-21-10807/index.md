# [백준]10807 개수 세기

https://www.acmicpc.net/problem/10807

# 풀이:

입력으로 주어진 N개의 정수 중에 v가 몇 개인지 출력한다.



# **코드:** 

사용언어 : c
```c
n,m,a[202];
main(){
    scanf("%d",&n);
    while(n--){
        scanf("%d",&m);
        a[m+100]++;
    }
    scanf("%d",&n);
    printf("%d\n",a[n+100]);
}
```


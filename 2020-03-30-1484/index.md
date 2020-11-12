# [백준]1484 다이어트

https://www.acmicpc.net/problem/1484

# 풀이:

a를 1로 b를  ( n + 1)^1/2 로 초기화 시킨다.

b^2 - a^2 이 n 과 같다면, b 를 출력한다.

b^2 - a^2 이 n 보다 작다면 b 를 +1 해준다.

b^2 - a^2 이 n 이상이라면, a 를 +1 해준다.

b와 a가 같아질떄까지 반복한다.

만약 출력을 한번도 안했다면 "-1"을 출력한다.



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
#include <math.h>
using namespace std;
int n,a=1,b,c;
int main(){
    cin>>n;
    for(b=sqrt(n+a);a!=b;){
        if(b*b-a*a==n)c=1,printf("%d\n",b);
        if(b*b-a*a<n)b++;
        else a++;
    }
    if(!c)puts("-1");
}
```


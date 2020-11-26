# [프로그래머스]약수의 합

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 정수 n의 모든 약수의 합을 리턴한다.

# **코드:**
사용언어 : c++
```c++
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

int solution(int n) {
    int answer = 0;
    for (int i = 1;i <= n;i++)
		if (n % i == 0)
			answer += i;
    return answer;
}
```


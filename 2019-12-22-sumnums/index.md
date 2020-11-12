# [프로그래머스]두 정수 사이의 합

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 두 수 a, b 사이에 속한 모든 정수의 합을 리턴한다.
2. a와 b는 -10,000,000 이상 10,000,000 이하인 정수 이므로 주의한다.
3. a와 b의 대소관계가 정해져 있지 않으므로 절댓값을 이용한다.

# **코드:**
사용언어 : c++
```c++
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

long long solution(int a, int b) {
    long long answer = ((long)a + (long)b) * (abs((long)b - (long)a) + 1) / 2;
    return answer;
}
```


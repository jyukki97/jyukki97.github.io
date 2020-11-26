# [프로그래머스]자연수 뒤집어 배열로 만들기

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열을 리턴한다.

# **코드:**
사용언어 : c++
```c++
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

int* solution(long long n) {
    // 리턴할 값은 메모리를 동적 할당해주세요.
    int* answer = (int*)malloc(sizeof(int)*12 + 1);
	int c = 0;
	while (n) {
		answer[c] = n % 10;
		n /= 10;
		c++;
	}
    return answer;
}
```


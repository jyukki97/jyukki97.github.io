# [프로그래머스]2016년

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 매 달 날짜를 계산하여 원하는 날짜의 요일을 구한다,

# **주의사항:**

1. 2016년은 윤년이다.
2. 1월 1일은 금요일이다.

# **코드:**
사용언어 : c++
```c++
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

char* solution(int a, int b) {
    // 리턴할 값은 메모리를 동적 할당해주세요.
    int m[13] = { 0,31,29,31,30,31,30,31,31,30,31,30,31 };
	const char *d[8]= { "THU","FRI","SAT","SUN","MON","TUE","WED" };
	for(int i = 1;i < a;i++) {
		b += m[i];
	}
	b %= 7;
    return d[b];
}
```


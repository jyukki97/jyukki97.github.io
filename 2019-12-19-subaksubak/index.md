# [프로그래머스]수박수박수박수박수박수?

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. "수박수박수..." 의 패턴을 유지하는 n만큼의 길이의 문자열을 리턴한다. 

# **코드:**
사용언어 : c++
```c++
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
#include <string.h>

char* solution(int n) {
	bool c = true;
	char a[] = "수";
	char b[] = "박";
	char* answer = (char*)malloc(sizeof(char)*3*n + 1);
	for (int i = 0;i < 3*n;i+=3) {
		if (c) {
			strcpy(answer + i, a);
			c = false;
		}
		else {
			strcpy(answer + i, b);
			c = true;
		}
	}
    return answer;
}
```


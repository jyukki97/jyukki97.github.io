# [프로그래머스]자릿수 더하기

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 자연수 n의 각 자릿수의 합을 구해서 리턴한다.

# **코드:**
사용언어 : c++
```c++
#include <iostream>

using namespace std;
int solution(int n)
{
    int answer = 0;

	while (n != 0) {
		answer += n % 10;
		n /= 10;
	}
    
    return answer;
}
```


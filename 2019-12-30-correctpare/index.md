# [프로그래머스]올바른 괄호

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

괄호가 바르게 짝지어졌다는 것은 '(' 문자로 열렸으면 반드시 짝지어서 ')' 문자로 닫혀야 한다는 뜻입니다. 예를 들어



- ()() 또는 (())() 는 올바른 괄호입니다.
- )()( 또는 (()( 는 올바르지 않은 괄호입니다.



'(' 또는 ')' 로만 이루어진 문자열 s가 주어졌을 때, 문자열 s가 올바른 괄호이면 true를 return 하고, 올바르지 않은 괄호이면 false를 return 하는 solution 함수를 완성해 주세요.



# 풀이:

스택이 비었거나 '(' 가 나온다면 스택에 push()

둘 다 아니면서 스택에 맨 위값이 '(' 라면 pop()

스택이 비었으면 올바른 괄호

  

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <iostream>
#include <stack>
using namespace std;

bool solution(string s)
{
	stack<char> a;
	for (char c : s) {
		if (a.empty() || c == '(')	
			a.push(c);
		else if (a.top() == '(')
			a.pop();
	}
    return a.empty();
}
```


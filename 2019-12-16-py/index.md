# [프로그래머스]문자열 내 p와 y의 개수

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 문자열 s의 모든 원소를 보고 p,P 이면 p의 갯수를 올리고, y,Y이면 y의 갯수를 올린다.
2. p의 갯수와 y의 갯수가 같다면 true 다르다면 false 를 리턴한다.

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <iostream>
using namespace std;

bool solution(string s)
{
    bool answer = true;
    int p = 0;
    int y = 0;
    for (int i = 0;i < s.length();i++) {
        if (s[i] == 'p' || s[i] == 'P') {
            p++;
        }
        if (s[i] == 'y' || s[i] == 'Y') {
            y++;
        }
    }
    if (p != y)
        answer = false;
    return answer;
}
```


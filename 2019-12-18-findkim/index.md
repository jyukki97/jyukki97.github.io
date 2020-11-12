# [프로그래머스]서울에서 김서방 찾기

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. string 배열 seoul의 원소 중 "Kim"의 위치를 찾아 반환한다.

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

string solution(vector<string> seoul) {
    for (int i = 0;i < seoul.size();i++)
        if (seoul[i] == "Kim")
            return "김서방은 " + to_string(i) + "에 있다";
}
```


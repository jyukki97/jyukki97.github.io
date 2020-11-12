# [프로그래머스]하샤드 수

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

양의 정수 x가 하샤드 수이려면 x의 자릿수의 합으로 x가 나누어져야 합니다. 예를 들어 18의 자릿수 합은 1+8=9이고, 18은 9로 나누어 떨어지므로 18은 하샤드 수입니다. 자연수 x를 입력받아 x가 하샤드 수인지 아닌지 검사하는 함수, solution을 완성해주세요.



# 풀이:

정수 x의 각 자릿수의 합을 구한다.

정수 x를 구한 값으로 나누어 나머지가 0이라면 true를 0이 아니라면 false를 출력한다.



# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

bool solution(int x) {
    int c = 0;
    string a = to_string(x);
    for(char i : a)
        c += i - '0';
    return !(x % c);
}
```


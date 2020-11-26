# [프로그래머스]짝수와 홀수

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

정수 num이 짝수일 경우 Even을 반환하고 홀수인 경우 Odd를 반환하는 함수, solution을 완성해주세요.



# 풀이:

정수 num이 짝수면 "Even" 을 홀수라면 "Odd" 를 반환한다.



# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

string solution(int num) {
    return num % 2 ? "Odd" : "Even";
}
```


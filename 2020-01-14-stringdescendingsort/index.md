# [프로그래머스]문자열 내림차순으로 배치하기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

문자열 s에 나타나는 문자를 큰것부터 작은 순으로 정렬해 새로운 문자열을 리턴하는 함수, solution을 완성해주세요.
 s는 영문 대소문자로만 구성되어 있으며, 대문자는 소문자보다 작은 것으로 간주합니다.



# 풀이:

주어진 문자열을 내림차순으로 정렬한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

string solution(string s) {
    sort(s.begin(), s.end(), greater<char>());
    return s;
}
```


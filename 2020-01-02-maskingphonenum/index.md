# [프로그래머스]핸드폰 번호 가리기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

프로그래머스 모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다.
 전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 `*`으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.



# 풀이:

문자열 phone_number 의 뒤에 4자리를 제외한 나머지 숫자를 전부 '*' 로 바꾼 후 리턴한다.



# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

string solution(string phone_number) {
	for (int i = 0;i < phone_number.size()-4;i++)
        phone_number[i] = '*';
    return phone_number;
}
```


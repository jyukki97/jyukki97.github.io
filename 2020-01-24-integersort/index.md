# [프로그래머스]정수 내림차순으로 배치하기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

함수 solution은 정수 n을 매개변수로 입력받습니다. n의 각 자릿수를 큰것부터 작은 순으로 정렬한 새로운 정수를 리턴해주세요. 예를들어 n이 118372면 873211을 리턴하면 됩니다.



# 풀이:

정수 n을 string 에 담는다.

담아진 string 을 내림차순으로 정렬한다.

string을 <u>long long 값으로 변환</u> 후 리턴한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

long long solution(long long n) {
    string a = to_string(n);
    sort(a.begin(), a.end(), greater<char>());
    return stoull(a);
}
```


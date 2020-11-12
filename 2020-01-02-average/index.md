# [프로그래머스]평균 구하기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.



# 풀이:

배열 arr의 평균값을 리턴한다.



# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

double solution(vector<int> arr) {
    double answer = 0;
    for(int i : arr)
        answer += i;
    return answer / arr.size();
}
```


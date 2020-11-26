# [프로그래머스]문자열 내 마음대로 정렬하기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

문자열로 구성된 리스트 strings와, 정수 n이 주어졌을 때, 각 문자열의 인덱스 n번째 글자를 기준으로 오름차순 정렬하려 합니다. 예를 들어 strings가 [sun, bed, car]이고 n이 1이면 각 단어의 인덱스 1의 문자 u, e, a로 strings를 정렬합니다.



# 풀이:

n번째 글자를 기준으로 오름차순 정렬을 한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

vector<string> solution(vector<string> strings, int n) {
    vector<string> answer;
    for (int i = 0; i < strings.size(); i++) 
		strings[i].insert(0, string(1, strings[i][n]));
	sort(strings.begin(), strings.end());
	for (int i = 0; i < strings.size(); i++)
		strings[i].erase(0, 1);
    return strings;
}
```



# 깔끔한 코드:

사용언어 : c++

```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;
int i;

bool compare (string a, string b) {
    return a[i] == b[i] ? a < b : a[i] < b[i];
}

vector<string> solution(vector<string> strings, int n) {
    i = n;
    sort (strings.begin(), strings.end(), compare);
    return strings;
}
```



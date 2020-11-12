# [프로그래머스]가장 큰 수

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

0 또는 양의 정수가 주어졌을 때, 정수를 이어 붙여 만들 수 있는 가장 큰 수를 알아내 주세요.



예를 들어, 주어진 정수가 [6, 10, 2]라면 [6102, 6210, 1062, 1026, 2610, 2106]를 만들 수 있고, 이중 가장 큰 수는 6210입니다.



0 또는 양의 정수가 담긴 배열 numbers가 매개변수로 주어질 때, 순서를 재배치하여 만들 수 있는 가장 큰 수를 문자열로 바꾸어 return 하도록 solution 함수를 작성해주세요.



# 풀이:

int 배열을 string으로 바꿔서 정렬한다.

string[1] + string[0] > string[0] + string[1] 이라면 string[0]과 string[1] 값을 바꿔준다.

전체적으로 가장 큰 수가 될때까지 반복한다.

마지막에 0000같은 수가 나올 수 있으므로 맨 앞자리가 0이라면 "0"을 return 하도록 해준다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

string solution(vector<int> numbers) {	
    vector<string> a;
	for (int i : numbers)
		a.push_back(to_string(i));
	sort(a.begin(), a.end(), greater<string>());
	string answer;
	for (int i = 0; i < numbers.size() - 1; i++) {
		if (a[i + 1] + a[i] > a[i] + a[i + 1]) {
			swap(a[i], a[i + 1]);
			if (!i)
				i = -1;
			else
				i -= 2;
		}
	}
	for (string s : a)
		answer += s;
    if(answer[0] == '0')
        return "0";
    return answer;
}
```



# **더 나은 코드:**

사용언어 : c++

```c++
#include <algorithm>
#include <string>
#include <vector>

using namespace std;

bool compare(const string &a, const string &b)
{
    if (b + a < a + b)
        return true;
    return false;
}

string solution(vector<int> numbers) {
    string answer = "";

    vector<string> strings;

    for (int i : numbers)
        strings.push_back(to_string(i));

    sort(strings.begin(), strings.end(), compare);

    for (auto iter = strings.begin(); iter < strings.end(); ++iter)
        answer += *iter;

    if (answer[0] == '0')
        answer = "0";

    return answer;
}
```

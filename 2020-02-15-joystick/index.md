# [프로그래머스]조이스틱

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

조이스틱으로 알파벳 이름을 완성하세요. 맨 처음엔 A로만 이루어져 있습니다.
 ex) 완성해야 하는 이름이 세 글자면 AAA, 네 글자면 AAAA



조이스틱을 각 방향으로 움직이면 아래와 같습니다.



```
▲ - 다음 알파벳
▼ - 이전 알파벳 (A에서 아래쪽으로 이동하면 Z로)
◀ - 커서를 왼쪽으로 이동 (첫 번째 위치에서 왼쪽으로 이동하면 마지막 문자에 커서)
▶ - 커서를 오른쪽으로 이동
```



예를 들어 아래의 방법으로 JAZ를 만들 수 있습니다.



```
- 첫 번째 위치에서 조이스틱을 위로 9번 조작하여 J를 완성합니다.
- 조이스틱을 왼쪽으로 1번 조작하여 커서를 마지막 문자 위치로 이동시킵니다.
- 마지막 위치에서 조이스틱을 아래로 1번 조작하여 Z를 완성합니다.
따라서 11번 이동시켜 "JAZ"를 만들 수 있고, 이때가 최소 이동입니다.
```



만들고자 하는 이름 name이 매개변수로 주어질 때, 이름에 대해 조이스틱 조작 횟수의 최솟값을 return 하도록 solution 함수를 만드세요.



# 풀이:

현재 위치에서 왼쪽, 오른쪽 중 'A' 가 아닌 문자가 먼저 오는 곳으로 위치를 바꾼다.

바꾼 만큼 answer 값을 + 해준다.

현재 위치값에서  'A' 와의 차이와 'Z' 와의 차이 중 더 작은 것을 answer 에 +해준다.

현재 값을 'A'로 바꿔준다.

name값이 전부 'A' 라면 반복을 종료한다.



greedy로 풀이를 한 문제라 "ABABAAAAAAABA" 같은 값은 정확한 값을 도출하지 못한다. 그러나 문제에서 원하는 방식이 greedy라서 결과또한 greedy값을 원하는 것 같다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

int solution(string name) {
    string a(name.size(), 'A');
    int answer = 0, c = 0, r, l;
    while (name != a) {
        answer += min(name[c] - 'A', 'Z' - name[c] + 1);
        name[c] = 'A';
        for (int i = 1; i <= name.size() / 2; i++) {
            r = c + i;
            l = c - i;
            if (r >= name.size())   r -= name.size();
            if (l < 0)  l += name.size();
            if (name[r] != 'A') {
                answer += i;
                c = r;
                break;
            }
            else if (name[l] != 'A') {
                answer += i;
                c = l;
                break;
            }
        }
    }
    return answer;
}
```


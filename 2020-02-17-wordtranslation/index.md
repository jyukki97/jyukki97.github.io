# [프로그래머스]단어 변환

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

두 개의 단어 begin, target과 단어의 집합 words가 있습니다. 아래와 같은 규칙을 이용하여 begin에서 target으로 변환하는 가장 짧은 변환 과정을 찾으려고 합니다.



```
1. 한 번에 한 개의 알파벳만 바꿀 수 있습니다.
2. words에 있는 단어로만 변환할 수 있습니다.
```



예를 들어 begin이 hit, target가 cog, words가 [hot,dot,dog,lot,log,cog]라면 hit -> hot -> dot -> dog -> cog와 같이 4단계를 거쳐 변환할 수 있습니다.



두 개의 단어 begin, target과 단어의 집합 words가 매개변수로 주어질 때, 최소 몇 단계의 과정을 거쳐 begin을 target으로 변환할 수 있는지 return 하도록 solution 함수를 작성해주세요.



# 풀이:

배열 words에 target 단어가 없다면 0을 return 한다.

만약 begin 과 target의 단어가 한개의 알파벳만 다를때 까지 반복을 개시한다.

words의 들어 있는 배열 중 begin과 알파벳 하나 차이나는 단어를 찾는다.

begin을 그 단어로 바꾼 후 words에서 삭제한다.

answer 값을 +1 해준다.

반복이 끝난 후 answer + 1 을 return 해준다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

bool com(string a, string b) {
    int c = 0;
    for (int i = 0; i < a.size(); i++)
        if (a[i] == b[i])    c++;
    if (c == a.size() - 1)   return true;
    return false;
}

int solution(string begin, string target, vector<string> words) {
    int answer = 0;
    bool b = true;
    for (string s : words)
        if (s == target) {
            b = false;
            break;
        }
    if (b)   return answer;
    while (!com(begin, target)) {
        for (int i = 0; i < words.size(); i++) {
            if (com(begin, words[i])) {
                begin = words[i];
                answer++;
                words.erase(words.begin() + i);
                break;
            }
        }
    }
    return answer + 1;
}
```


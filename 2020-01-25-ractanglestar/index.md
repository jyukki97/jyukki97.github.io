# [프로그래머스]직사각형 별찍기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

이 문제에는 표준 입력으로 두 개의 정수 n과 m이 주어집니다.
 별(*) 문자를 이용해 가로의 길이가 n, 세로의 길이가 m인 직사각형 형태를 출력해보세요.



# 풀이:

n번 별을 찍는다. 개행한다.

그것을 m번 반복한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>

using namespace std;

int main(void) {
    int a, b;
    cin >> a >> b;
    for (int i = 0; i < b; i++){
        for (int t = 0; t < a; t++){
            cout << '*';
        }   
        cout << endl;
    }
    return 0;
}
```


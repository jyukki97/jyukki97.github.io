# [백준]11576 Base Conversion

https://www.acmicpc.net/problem/11576

# 풀이:

A진법으로 나타낸 수를 10진법으로 바꾼 후 바꾼 10진법 수를 다시 B진법으로 바꿔 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
using namespace std;
int a, b, m, n, s; vector<int> v;
int main() {
    cin >> a >> b >> m;
    while (m--) {
        cin >> n;
        s = s * a + n;
    }
    while (s)   v.push_back(s % b), s /= b;
    for (m = v.size() - 1; m >= 0; m--) cout << v[m] << " ";
    cout << endl;
}
```


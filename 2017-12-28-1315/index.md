# 1315 RPG

[https://www.acmicpc.net/problem/1315](http://www.acmicpc.net/problem/1315)

#### **풀이:**
1. a[i][t]
	: 힘이 i이고, 지력이 t일 때, 깰 수 있는 퀘스트의 수
2. 초기 능력치를 S, I 라고 했을 때, 깰 수 있는 퀘스트를 모두 클리어한다.
3. 클리어 한 후 모인 스텟 포인트를 힘과 지력에 포인트를 적절히 분배한다.
4. 분배한 힘과 지력으로 못 깬 퀘스트를 클리어 할 수 있는지 확인한다.

#### **주의 사항:**
1. 시간이 너무 많이 걸리므로 메모이제이션을 통해 a[i][t] 가 값을 가지고 있다면 바로 리턴하도록 만든다. 
2. 이전에 방문했었던 visit이 누적될 수 있으므로 초기화해주는 것을 잊지말자.
3. 포인트와 능력치를 더한값이 퀘스트 최대치인 1000을 넘어갈 수 있으므로, 1000으로 제한을 두자.

#### **코드:**

```
#include <iostream>
#include <vector>
#include <algorithm>
#include <string.h>
using namespace std;
int n;
int st[110], in[110], pn[110], visit[110] = { 0 }, a[1010][1010];
int rpg(int S, int I) {
	if (a[S][I] != -1)	return a[S][I];
	int po = 0, cnt = 0;
	vector <int> b;
	for (int i = 0; i < n; i++) {
		if ((S >= st[i] || I >= in[i])) {
			if (!visit[i]) {
				visit[i] = 1;
				po += pn[i];
				b.push_back(i);
			}
			cnt++;
		}
	}
	a[S][I] = cnt;
	for (int i = S; i <= min(1000,S + po); i++) {
		int t = min(1000, I + po - i + S);
		a[S][I] = max(a[S][I], rpg(i, t));
	}
	for (int i = 0; i < b.size(); i++)	visit[b[i]] = 0;
	return a[S][I];
}
int main(void) {
	cin >> n;
	memset(a, -1, sizeof a);
	for (int i = 0; i < n; i++)
		cin >> st[i] >> in[i] >> pn[i];
	cout << rpg(1, 1) << endl;
	return 0;
}
```

# [백준]9576 책 나눠주기

https://www.acmicpc.net/problem/9576

# 풀이:

학생들을 b 를 기준으로 정렬한다.

a[i] ~ b[i] 까지의 책들 중

현재 도서관에 있는 책이라면 빌려주고, 빌려준 학생수를 +1 해준다.

빌려준 학생수를 출력한다.



# **코드:** 

사용언어 : c++	
```c++
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;
int T,N,M,q,w,s,a[1005];
int main() {
	cin>>T;
	while (T--){
		cin>>N>>M;
		fill(a,a+1001,0);
        vector<pair<int, int>>v;
		for(s=0;M--;v.push_back({w,q}))
			cin>>q>>w;
		sort(v.begin(),v.end());
		for (auto i:v)
			for (q=i.second;q<=i.first;q++)
				if(!a[q]){
					a[q]=1,s++;
                    break;
                }
		cout<<s<<endl;
    }
}
```


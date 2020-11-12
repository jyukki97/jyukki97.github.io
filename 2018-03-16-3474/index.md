# 3474 교수가 된 현우

[https://www.acmicpc.net/problem/3474](http://www.acmicpc.net/problem/3474)

#### **풀이:**
1. 오른쪽 끝에있는 0에 갯수를 알기 위해서는 팩토리얼 안에서 10의 갯수가 얼마나 있는지를 알면된다.
2. 이 때 2의 갯수는 매우 많으므로 팩토리얼 내에서 5가 몇번 곱해지는지를 세면 간단하게 알 수 있다.
3. 주어진 수를 5로 나눈 몫이 5의 갯수이다
4. 그러나 25, 125 등 5가 여러번 들어가는 경우도 있으므로
5. 각각으로 나누어준 값을 더해주어야한다.
 

#### **코드:**
사용언어 : Python 3
{% highlight Python %}
for i in range(int(input())):
    a,b,c=int(input()),5,0
    while b<=a:
        c+=a//b
        b*=5
    print(c)
{% endhighlight %}

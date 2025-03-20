# recursion


```c++

```
```c++
#include<bits/stdc++.h>
using namespace std;
int fib(int n){
	if(n <= 1){
		return n;
	}
	return fib(n-1)+fib(n-2);
}
int main(){
	int n = 10;
	cout<<"fibonachi("<<n<<") = "<<fib(n)<<endl;
}
```

# Recursive Solution with Memoization (DP - Top Down)

```c++
#include<bits/stdc++.h>
using namespace std;
vector<int>dp(1000 , -1);
int fib(int n){
	if(n <= 1)return n;
	if(dp[n] != -1)return dp[n];
	return dp[n] = fib(n-1)+fib(n-2);#include<bits/stdc++.h>
using namespace std;
int fib(int n){
	if(n <= 1){
		return n;
	}
	return fib(n-1)+fib(n-2);
}
int main(){
	int n = 10;
	cout<<"fibonachi("<<n<<") = "<<fib(n)<<endl;
}
}
int main(){
	int n = 10;
	cout<<fib(n)<<endl;
	return 0;
}
```

# Iterative Solution (DP - Bottom Up)

```c++
#include<bits/stdc++.h>
using namespace std;
int fib(int n){
	vector<int>dp(n+1);
	dp[0] = 0;
	dp[1] = 1;
	for(int i = 2; i<= n; i++){
		dp[i] = dp[i-1]+dp[i-2];
	}
	return dp[n];
}
int main(){
	int n= 10;
	cout<<fib(n)<<endl;
	return 0;
}
```
# bf-code

```c++
#include<bits/stdc++.h>
using namespace std;
int main(){
	int n;
	cin>>n;
	int a = 0 , b = 1;
	cout<<"fibonachi series: "<<a<<" "<<b<<" ";
	for(int i = 2; i<= n; i++){
		int next = a+b;
		cout<<next<<" ";
		a = b;
		b = next;
	}
	cout<<endl;
	return 0;
}
```


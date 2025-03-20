#how to swap two numbers
```c++
#include<bits/stdc++.h>
using namespace std;
int main(){
    int a = 3;
    int b = 4;
    a = a^b;
    b = a^b;
    a = a^b;
    cout<<a<<endl;
    cout<<b<<endl;
}
```


# check if two numbers are equal or not 

```c++
#include<bits/stdc++.h>
using namespace std;
int main(){
    int a = 4;
    int b = 5;
    cout<<!(a^b);
}
```

# find the count of numbers
```c++
#include <bits/stdc++.h> // For log10()
using namespace std;

int main() {
    int n = 56;
    cout << (int)(log10(n) + 1);  // Correct way to count digits
    return 0;
}
```
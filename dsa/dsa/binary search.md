## Binary Search Working

Binary Search Algorithm can be implemented in two ways which are discussed below.

1. Iterative Method
2. Recursive Method

The recursive method follows [the divide and conquer](https://www.programiz.com/dsa/divide-and-conquer) approach.

The general steps for both methods are discussed below.

1. The array in which searching is to be performed is:![[binary-search-initial-array.webp]]![[binary-search-set-pointers.webp]]![[binary-search-mid.webp]]![[binary-search-find-mid.webp]]
```c++
#include"bits/stdc++.h"

using namespace std;

int binarysearch(int arr[] , int x , int low , int high){

while(low <= high){

int mid = low+(high-low)/2;

if(x == arr[mid]){

return mid;

}

if( x > arr[mid]){

low = mid+1;

}

else high = mid-1;

}

return -1;

}

int main(){

ios::sync_with_stdio(0);

cin.tie(0);

cout.tie(0);

int arr[] = { 3, 4, 6, 7, 8, 9 , 1, 4 , 7};

int x= 4;

int n = sizeof(arr)/sizeof(arr[0]);

int result = binarysearch(arr , x , 0 , n-1);

if(result == -1){

cout<<"not found";

}

else{

cout<<result<<endl;

}

return 0;

}
```

### recursive method

```c++
#include"bits/stdc++.h"

using namespace std;

int binarysearch(int arr[] , int target , int low , int high){

if(high >= low){

int mid = low+(high-low)/2;

if(target == arr[mid]){

return mid;

}

if(target > arr[mid]){

return binarysearch(arr , target, mid+1 , high);

}

return binarysearch(arr , target , low , mid-1);

}

return -1;

}

int main(){

ios::sync_with_stdio(0);

cin.tie(0);

cout.tie(0);

int arr[] = { 3 , 6, 5, 7, 8, 9, 2, 1,4};

int target = 4;

int n= sizeof(arr)/sizeof(arr[0]);

int result = binarysearch(arr , target , 0 , n-1);

if(result == -1){

cout<<"not found";

}

else{

cout<<"element is found"<<result;

}

}
```

## Binary Search Complexity

**Time Complexities**

- **Best case complexity**: `O(1)`
- **Average case complexity**: `O(log n)`
- **Worst case complexity**: `O(log n)`

**Space Complexity**

The space complexity of the binary search is `O(1)`.


## book allocation to students

```c++
#include<bits/stdc++.h>

using namespace std;

bool canbeplaced(vector<int>&p , int m, int threshold){

int n = p.size(), k = 1, pages = 0;

for(int i = 0; i<n; i++){

pages += p[i];

if(pages>threshold){

pages = 0;

k++;

i--;

if(k > m)return false;

}

}

return true;

}

int books(vector<int>&p , int m){

if(m >p.size())return -1;//not enough books

int l = 0, r = 0, ans = -1, n = p.size();

for(int i = 0; i<n; i++){

r+= p[i];

}

while(l <= r){

int mid = (l+r)/2;

if(canbeplaced(p , m , mid)){

ans = mid;

r = mid-1;

}

else{

l = mid+1;

}

}

return ans;

}

int main(){

ios::sync_with_stdio(0);

cin.tie(0);

cout.tie(0);

vector<int>books = {12 , 34, 67 , 90};

int students = 2;

cout<<"minimum possible maximum pages:"<<books(books, students)<<endl;

return 0;

}
```
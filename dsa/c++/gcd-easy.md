### **Note on GCD Calculation Using Euclidean Algorithm in C++**

---

### **Code Explanation**

```cpp
#include<bits/stdc++.h>
using namespace std;

// Function to calculate GCD using the Euclidean algorithm
int gcding(int a, int b) {
    if (b == 0) {
        return a;  // Base case: GCD is 'a' when 'b' becomes zero
    } else {
        return gcding(b, a % b);  // Recursive call with (b, a % b)
    }
}

int main() {
    int a = 90, b = 54;  // Sample values
    cout << gcding(a, b); // Output the GCD
    return 0;
}
```

---

### **How the Code Works**

✅ **`#include<bits/stdc++.h>`** — This header includes all standard libraries for convenience in competitive programming.

✅ **`using namespace std;`** — This avoids the need to prefix `std::` before standard functions like `cout` or `cin`.

✅ **Function `gcding(int a, int b)`** — This function implements the **Euclidean Algorithm** to calculate the GCD (Greatest Common Divisor).

- **Base Case:** If `b == 0`, return `a` as the GCD.
- **Recursive Step:** Call `gcding(b, a % b)` until `b` becomes zero.

✅ **In `main()` Function:**

- `a = 90` and `b = 54` are initialized.
- The `gcding()` function is called, and the result is printed using `cout`.

---

### **Working of Euclidean Algorithm**

The Euclidean Algorithm is based on the principle:

gcd⁡(a,b)=gcd⁡(b,amod  b)\gcd(a, b) = \gcd(b, a \mod b)

**Example:** Finding GCD of **90** and **54**

- Step 1: `gcd(90, 54)` → Calls `gcd(54, 90 % 54)` → `gcd(54, 36)`
- Step 2: `gcd(54, 36)` → Calls `gcd(36, 54 % 36)` → `gcd(36, 18)`
- Step 3: `gcd(36, 18)` → Calls `gcd(18, 36 % 18)` → `gcd(18, 0)`
- Step 4: Since `b == 0`, return **18** as the GCD.

---

### **Sample Output**

```
18
```

---

### **Complexity Analysis**

- **Time Complexity:** `O(log(min(a, b)))` — Very efficient for large numbers.
- **Space Complexity:** `O(1)` for iterative; `O(log(min(a, b)))` for recursive (due to stack frames).

---

### **Key Takeaways**

✅ Uses the efficient **Euclidean Algorithm**.  
✅ Recursive implementation keeps the code clean and intuitive.  
✅ Highly efficient for calculating GCD in large numbers.

---

### **Additional Tip**

For modern C++, you can also use the in-built GCD function from `<algorithm>` like this:

```cpp
#include <iostream>
#include <algorithm> // For std::gcd
using namespace std;

int main() {
    int a = 90, b = 54;
    cout << gcd(a, b); // In-built function in C++17 or later
    return 0;
}
```

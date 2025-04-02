# Rotate an Array

```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
  public:
    // Function to rotate an array by d elements in counter-clockwise direction.
    void rotateArr(vector<int>& arr, int d) {
        int n = arr.size();
        d = d % n;
        int sub[d];
        
        for(int i = 0; i < d; i++) {
            sub[i] = arr[i];
        }
        
        for(int i = 0; i < n - d; i++) {
            swap(arr[i + d], arr[i]);
        }
        
        for(int i = n - d, j = 0; i < n; i++, j++) {
            arr[i] = sub[j];
        }
    }
};
```


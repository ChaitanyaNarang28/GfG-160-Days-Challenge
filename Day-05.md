# Next Permutation

```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
  public:
    void nextPermutation(vector<int>& arr) {
        int n = arr.size();
        int i = n - 2, j = n - 1;
        
        while (i >= 0 && arr[i] >= arr[i + 1])
            i--;
        
        if (i >= 0) {
            while (arr[j] <= arr[i]) {
                j--;
            }
            swap(arr[i], arr[j]);
        }
        
        int start = i + 1, end = n - 1;
        while (start < end) {
            swap(arr[start], arr[end]);
            start++;
            end--;
        }
    }
};
```


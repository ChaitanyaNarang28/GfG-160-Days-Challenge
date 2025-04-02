# Second Largest Element in an Array

```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution
{
    public:
    int secondLargest(vector<int>& arr)
    {
        int n = arr.size();
        if(n < 2)
            return -1;
        
        for(int i = 0; i < n; i++)
        {
            for(int j = 0; j < n - i - 1; j++)
            {
                if(arr[j] > arr[j + 1])
                {
                    swap(arr[j], arr[j + 1]);
                }
            }
        }
        return arr[n - 2];
    }
};
```


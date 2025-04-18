# *Find H-Index*

```cpp
class Solution {
  public:
    // Function to find hIndex
    int hIndex(vector<int>& citations) {
        int n=citations.size();
        vector<int> buckets(n+1,0);
        
        for(int c: citations)
        {
            if(c>=n) buckets[n]++;
            
            else buckets[c]++;
        }
        
        int cum=0;
        for(int i=n;i>=0;--i)
        {
            cum+=buckets[i];
            if(cum>=i) return i;
        }
        
        return 0;
    }
};
```

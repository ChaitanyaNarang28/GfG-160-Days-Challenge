# *Maximum Product Subarray*

```cpp

class Solution {
  public:
    // Function to find maximum product subarray
    int maxProduct(vector<int> &arr) {
        int n=arr.size();
        int maxp=arr[0];
        int minp=arr[0];
        int maxi=arr[0];
        
        for(int i=1;i<n;i++)
        {
            if(arr[i]<0) swap(maxp,minp);
            
            maxp=max(arr[i],(maxp*arr[i]));
            minp=min(arr[i],(minp*arr[i]));
            maxi=max(maxi,maxp);
            
        }
        
        return maxi;
    }
};

```

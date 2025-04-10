# *Max Circular Subarray Sum*

```cpp

class Solution {
  public:
    // arr: input array
    // Function to find maximum circular subarray sum.
    int circularSubarraySum(vector<int> &arr) {

        int total=0,maxs=INT_MIN,mins=INT_MAX;
        int cmax=0,cmin=0;
        bool alln=true;
        for(int num:arr)
        {
            total=total+num;
            cmax=max(num,cmax+num);
            maxs=max(maxs,cmax);
            cmin=min(num,cmin+num);
            mins=min(mins,cmin);
            
            if(num>0) alln=false;
           
        }
        
        if(alln) return maxs;
        return max(maxs,total-mins);
    }
};


```

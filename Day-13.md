# *Smallest Positive Missing

```cpp

class Solution {
  public:
    // Function to find the smallest positive number missing from the array.
    int missingNumber(vector<int> &arr) {
        int n=arr.size();
        int cnt=1;
        sort(arr.begin(),arr.end());
        
        for(int i=0;i<n;i++)
        {
            if(arr[i]<=0)
            {
                continue;
            }
            
            if(cnt<arr[i])
            {
                return cnt;
                
                break;
            }
            else if(cnt==arr[i]) cnt++;
                
        }
        
        return cnt;
            
        }

```
        
};

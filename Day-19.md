# *Min Chars to Add for Palindrome*

``` cpp

class Solution {
  public:
    int minChar(string& s) {
        int n=s.length();
        string revStr=s;
        reverse(revStr.begin(),revStr.end());
        
        string combined=s+ "$" +revStr;
        int m=combined.length();
        
        vector<int> lps(m,0);
        for(int i=1;i<m;i++)
        {
            int j=lps[i-1];
            while(j>0 && combined[i]!=combined[j])
            {
                j=lps[j-1];
            }
            if(combined[i]==combined[j])
            {
                j++;
            }
            
            lps[i]=j;
        }
        
        return n-lps.back();
    }
};
```


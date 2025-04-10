# *Implement Atoi*

```cpp

class Solution {
  public:
    int myAtoi(char *s) {
        int i=0,sign=1;
        long res=0;
        
        while(s[i]==' ') i++;
        if(s[i]=='-' || s[i]=='+')
        {
            sign=(s[i++]=='-') ? -1:1;
        }
        
        while(s[i]>='0' && s[i]<='9')
        {
            res=res*10 +(s[i++]-'0');
            
            if(res*sign>INT_MAX) return INT_MAX;
            if(res*sign<INT_MIN) return INT_MIN;
        }
        
        return static_cast<int>(res*sign);
    }
};

```

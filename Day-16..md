# *Anagram*

```cpp

class Solution {
  public:
    // Function is to check whether two strings are anagram of each other or not.
    bool areAnagrams(string& s1, string& s2) {
        if(s1.length()!=s2.length()) return false;
        int counts[26]={0};
        for(int i =0;i<s1.length();i++)
        {
            counts[s1[i]-'a']++;
            counts[s2[i]-'a']--;
        }
        
        for(int count:counts)
        {
            if(count!=0) return false;
        }
        return true;
    }
};

```

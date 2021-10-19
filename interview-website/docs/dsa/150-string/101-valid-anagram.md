---
sidebar_position : 101
tags:
  - String
  - Easy
---

#   Valid Anagram

Given two strings s and t, return true if t is an anagram of s, and false otherwise.

Example 1:

```
Input: s = "anagram", t = "nagaram"
Output: true
```

Example 2:

```
Input: s = "rat", t = "car"
Output: false
```

Constraints:

- `1 <= s.length, t.length <= 5 * 104`
- `s` and `t` consist of lowercase English letters.

# Approach 1

- Create a character array for both the strings of size 26
- Fill the arrays value based on each character in the strings
- Compare the characters with each for equality

## Solution

```java
class Solution {
    public boolean isAnagram(String s, String t) {

        char[] cs = new char[26];

        for(char c : s.toCharArray()){
            cs[c - 'a']++;
        }

        char[] ct = new char[26];

        for(char c : t.toCharArray()){
            ct[c - 'a']++;
        }

        return String.valueOf(cs).equals(String.valueOf(ct));
    }
}
```

# Approach 2

- Use a HashMap to fill the values for the first string
  - key : character, value : number of times occurrence
- for second string, keep on decrementing the value if there is matching key
- Check if the HashMap is empty or not

## Solution

```java
class Solution {
    public boolean isAnagram(String s, String t) {

        Map<Character, Integer> map = new HashMap<>();

        for(char c: s.toCharArray()){
            int val = map.getOrDefault(c, 0);
            map.put(c, val+1);
        }

        for(char c : t.toCharArray()){

            if(!map.containsKey(c))
                return false;

            int val = map.get(c);
            val--;

            if(val == 0){
                map.remove(c);
            } else{  
                map.put(c, val);
            }
        }

        if(map.isEmpty()) return true;

        return false;
    }
}
```




---

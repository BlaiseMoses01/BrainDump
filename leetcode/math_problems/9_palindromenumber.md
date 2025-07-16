My Solution in C++ 

```cpp
class Solution {
public:
    bool isPalindrome(int x) {
        long reverse = 0; 
        int og = x;  

        while(x > 0){
            reverse = reverse*10 + (x%10);
            x /= 10;
        }
        if(reverse == og) return true; 
        else return false; 
    }
};

```
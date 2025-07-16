My Solution in C++ 

```cpp
class Solution {
public:
    int trailingZeroes(int n) {
        if(n == 0 || n == 1) return 0 ;

        long long zeros = 0 ; 
        while( n > 0 ){
            n /= 5;
            zeros += n;
        }
        return zeros; 
    }
};

```
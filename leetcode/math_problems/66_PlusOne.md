My Solution in C++ 

```cpp
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        for(int i = digits.size()-1 ; i >= 0; i--){
            if(digits[i] < 9) {
                digits[i]++;
                return digits; 
            }
            else{
                digits[i] = 0; 
                continue;
            }
        } 
        vector<int> carriedDigits(digits.size()+1,0);
        carriedDigits[0] =1 ; 
        return carriedDigits; 
    }
};

```
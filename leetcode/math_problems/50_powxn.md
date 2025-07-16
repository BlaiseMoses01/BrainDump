My Solution in C++ 

```cpp
class Solution {
public:
    double myPow(double x, int n) {
      // After some reading to figure out a way to optimize,  read  
      // about Binary Exponentization, method to do 
      // exponentiation in O(logn) instead of O(n)

      /*
      * odd exp formula : x * (x*x) ^ n-1/2 
      * even exp formula : (x*x) ^ n/2
      */ 
        double ret =  myPowRecursive(x,n);
        if(n < 0) return 1/ret;
        else return ret; 

    }
    double myPowRecursive(double x , int n ){
        if(n == 0) return 1; 

        double res = myPowRecursive(x , n/2);

        if(n % 2)
            return res*res*x;
        else
            return res*res;
    } 

    void myPowNaiive(double x,  int n ){
      /*
        * A few things to think about here 
        * if the exponent is negative, we need to do 1/ whatever base^exp is 
        * if the base is negative , even exp result stays same,  negative is negative . 
        * need to use absolute values if we want to use the same loops 
        */
       bool negExp= false;
       if(n < 0) negExp = true; 
       int abs_n = abs(n); 

        double naked_result = 1; 
        for(int i = 0 ; i < abs_n ; i++){
            naked_result *= x;
        }
        if(negExp) {
            naked_result = 1/naked_result;
        }
        //return naked_result; 
    }
};

```
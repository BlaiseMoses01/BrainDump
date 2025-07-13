# Fisher-Yates Sorting Algorithm
**Written by Blaise Moses July 13th, 2025**

---

**input** : Vector or Array of objects
**time complexity** : O(n) 
**space complexity** : O(1)

**Application** : Used to shuffle a vector or array in place in linear time. When paired with a robust RNG results in perfect uniformity with all permutation being equally likely.

### Example Implementation : 

```
/*
 * Fisher-Yates Shuffle Algorithm Example 
 * Implements a Fisher Yates Shuffle Algorithm , the same algorithm used by std::shuffle
 * Written by Blaise Moses July 13th 2025
 */
#include<stdlib.h> 
#include<time.h>
#include<bits/stdc++.h> 
#include<vector> 
#include<random>

/* helper function to preform a register swap
 * NOTE : can forgoe the need for this by using std::swap , but it's good to know how to do it manually.
 */
void swap ( int *a,  int *b)
{
    int temp = *a;
    *a = *b;
    *b = temp;     
} 

// helper to print the vector 
void printVect(std::vector<int> v)
{
    std::cout << "{ ";
    for(auto val : v){
        std::cout << val << " ";  
    }
    std::cout << "}\n"; 
}
/* implements the Fisher Yates Algorithm to randomly shuffle vector in O(n). 
 * The algorith works by starting at the end of the vector , randomly swapping two elements, then
 * iteratively reducing the swap window by 1 until it reaches the front of the vector
 */
void fisherYatesShuffler(std::vector<int> &v)
{
    std::random_device rd;
    std::mt19937 rng(rd());
    for(int i = v.size()-1 ; i > 0 ; i--){
        std::uniform_int_distribution<int> dist(0,i);
        int j = dist(rng);
        //swap(&v[i], &v[j]);
        std::swap(v[i], v[j]); 
    }
}


int main(void)
{
    std::vector<int> v = {1,2,3,4,5,6,7,8}; 
    std::cout << "Original: ";
    printVect(v);
    fisherYatesShuffler(v);
    std::cout << "Shuffled: ";
    printVect(v);
}
```
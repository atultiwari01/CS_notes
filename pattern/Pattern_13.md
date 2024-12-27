# Pattern_13
```
5
5 4
5 4 3
5 4 3 2
5 4 3 2 1
```

---

### Code:
```cpp
#include<iostream>
using namespace std;
int main(){
    for(int row =5; row>=1 ; row--){
        for(int col = 5; col>=row ; col--){
            cout<<col<<" ";
        }
        cout<<endl;
    }
    return 0;
}
```
### Logic:
This program prints a pattern of numbers in descending order, where the starting number decreases with each row. Here's the detailed explanation of the logic:

---

### Code Explanation

1. **Outer Loop (Row Loop):**
   ```cpp
   for(int row = 5; row >= 1; row--) {
   ```
   - The outer loop determines the number of rows in the pattern.
   - `row` starts at `5` and decrements to `1`, creating 5 rows in total.

2. **Inner Loop (Column Loop):**
   ```cpp
   for(int col = 5; col >= row; col--) {
   ```
   - The inner loop determines the numbers printed in each row.
   - `col` starts at `5` and decrements down to the current value of `row`.
   - For example:
     - When `row = 5`, `col` runs from `5` to `5` → prints `5`.
     - When `row = 4`, `col` runs from `5` to `4` → prints `5 4`.
     - When `row = 3`, `col` runs from `5` to `3` → prints `5 4 3`.
     - This pattern continues until `row = 1`.

3. **Printing Numbers:**
   ```cpp
   cout << col << " ";
   ```
   - During each iteration of the inner loop, the value of `col` (starting from `5` and decreasing to the current `row`) is printed, followed by a space.

4. **Newline After Each Row:**
   ```cpp
   cout << endl;
   ```
   - After completing the inner loop for one row, a newline character is printed to move to the next row.

---

### Program Output

The output of the program will be:

```
5
5 4
5 4 3
5 4 3 2
5 4 3 2 1
```

---

### Key Points
1. The **outer loop** determines the row number and the minimum value to be printed in that row (`row`).
2. The **inner loop** prints numbers starting from `5` down to the current `row` value.
3. Each row starts at `5` and decreases until it reaches the current row number.
4. A new line is added after printing all numbers in a row.

This program produces a triangular pattern of numbers, where each row contains descending numbers starting from `5`. The length of the row increases with each iteration, forming an inverted right-angled triangle.
# Pattern_15
```
        1
      2 2
    3 3 3
  4 4 4 4
5 5 5 5 5
```
### Code:
```cpp
#include<iostream>
using namespace std;
int main(){
    for(int row =1; row<=5 ; row++){
        for(int col = 1; col<=5-row ; col++){
            cout<<"  ";
        }
        for(int col = 1; col<=row ; col++){
            cout<<row<<" ";
        }
        cout<<endl;
    }
    return 0;
}
```
## Logic:
This program prints a right-aligned triangular pattern of numbers. Each row contains the same number repeated, which corresponds to the row number. Here's a detailed breakdown of the logic:

---

### Code Breakdown

1. **Outer Loop (Row Loop):**
   ```cpp
   for(int row = 1; row <= 5; row++) {
   ```
   - The outer loop controls the number of rows in the pattern.
   - `row` starts at `1` and increments to `5`, creating 5 rows in total.

2. **First Inner Loop (Spaces):**
   ```cpp
   for(int col = 1; col <= 5 - row; col++) {
       cout << "  ";
   }
   ```
   - This loop prints spaces before the numbers to align the pattern to the right.
   - The condition `col <= 5 - row` ensures that the number of spaces decreases as the row number increases:
     - For `row = 1`, `5 - row = 4` → 4 spaces.
     - For `row = 2`, `5 - row = 3` → 3 spaces.
     - This continues until `row = 5`, where no spaces are printed.

3. **Second Inner Loop (Numbers):**
   ```cpp
   for(int col = 1; col <= row; col++) {
       cout << row << " ";
   }
   ```
   - This loop prints the numbers for the current row.
   - The condition `col <= row` ensures that the number of numbers equals the current row number:
     - For `row = 1`, the number `1` is printed once.
     - For `row = 2`, the number `2` is printed twice.
     - This continues until `row = 5`, where the number `5` is printed five times.

4. **Newline After Each Row:**
   ```cpp
   cout << endl;
   ```
   - After completing the loops for one row, a newline character is printed to move to the next row.

---

### Program Output

The output of the program will be:

```
        1
      2 2
    3 3 3
  4 4 4 4
5 5 5 5 5
```

---

### Key Points

1. **Outer Loop:**
   - Determines the row number.
   - Controls the execution of the inner loops for each row.

2. **First Inner Loop (Spaces):**
   - Prints spaces to shift the numbers to the right.
   - The number of spaces decreases as the row number increases.

3. **Second Inner Loop (Numbers):**
   - Prints the current row number repeated for the row count.
   - The number of repetitions equals the current row number.

4. **Right Alignment:**
   - The combination of spaces and numbers creates a right-aligned triangular pattern.

This program effectively creates a triangle where each row's number increases from top to bottom, and the numbers are aligned to the right.
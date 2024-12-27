# Pattern_18
```
        1
      2 1
    3 2 1
  4 3 2 1
5 4 3 2 1
```
## Code:
```
#include<iostream>
using namespace std;
int main(){
    for(int row =1; row<=5 ; row++){
        for(int col = 1; col<=5-row ; col++){
            cout<<"  ";
        }
        for(int col = row; col>=1 ; col--){
            cout<<col<<" ";
        }
        cout<<endl;
    }
    return 0;
}
```
## Logic:
This program prints a right-aligned triangular pattern of numbers. Each row contains numbers starting from the current row number and decreasing to `1`. Here's a detailed explanation of the logic:

---

### Code Breakdown

1. **Outer Loop (Row Loop):**
   ```cpp
   for(int row = 1; row <= 5; row++) {
   ```
   - The outer loop determines the number of rows in the pattern.
   - `row` starts at `1` and increments up to `5`, creating 5 rows in total.

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
   for(int col = row; col >= 1; col--) {
       cout << col << " ";
   }
   ```
   - This loop prints numbers for the current row.
   - The condition `col >= 1` ensures that the numbers start from the current row number (`row`) and decrement to `1`:
     - For `row = 1`, the loop prints `1`.
     - For `row = 2`, the loop prints `2 1`.
     - For `row = 3`, the loop prints `3 2 1`.
     - This continues until `row = 5`, where the loop prints `5 4 3 2 1`.

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
      2 1
    3 2 1
  4 3 2 1
5 4 3 2 1
```

---

### Key Points

1. **Outer Loop:**
   - Determines the row number and controls the execution of the inner loops.

2. **First Inner Loop (Spaces):**
   - Prints spaces to align the numbers to the right.
   - The number of spaces decreases as the row number increases.

3. **Second Inner Loop (Numbers):**
   - Prints numbers starting from the current row number and decreasing to `1`.
   - The sequence of numbers in each row is reversed because the loop starts from `row` and decrements.

4. **Right Alignment:**
   - The combination of spaces and numbers creates a right-aligned triangular pattern.

This program generates a triangular pattern of decreasing numbers, aligned to the right, where each row starts with the row number and decrements to `1`.
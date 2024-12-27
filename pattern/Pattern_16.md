# Pattern_16
```
        1
      1 2
    1 2 3
  1 2 3 4
1 2 3 4 5
```
## Code:
```cpp
#include<iostream>
using namespace std;
int main(){
    for(int row =1; row<=5 ; row++){
        for(int col = 1; col<=5-row ; col++){
            cout<<"  ";
        }
        for(int col = 1; col<=row ; col++){
            cout<<col<<" ";
        }
        cout<<endl;
    }
    return 0;
}
```
## Logic:
This program generates a right-aligned triangular pattern of numbers. Each row contains numbers starting from `1` and increasing up to the current row number. Here's a detailed explanation of the logic:

---

### Code Breakdown

1. **Outer Loop (Row Loop):**
   ```cpp
   for(int row = 1; row <= 5; row++) {
   ```
   - The outer loop controls the number of rows in the pattern.
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
   for(int col = 1; col <= row; col++) {
       cout << col << " ";
   }
   ```
   - This loop prints the numbers for the current row.
   - The condition `col <= row` ensures that the numbers printed in each row go from `1` up to the current row number:
     - For `row = 1`, the loop prints `1`.
     - For `row = 2`, the loop prints `1 2`.
     - For `row = 3`, the loop prints `1 2 3`.
     - This pattern continues until `row = 5`, where the loop prints `1 2 3 4 5`.

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
      1 2
    1 2 3
  1 2 3 4
1 2 3 4 5
```

---

### Key Points

1. **Outer Loop:**
   - Determines the current row number and controls the execution of the inner loops.

2. **First Inner Loop (Spaces):**
   - Prints spaces to shift the numbers to the right.
   - The number of spaces decreases as the row number increases.

3. **Second Inner Loop (Numbers):**
   - Prints numbers from `1` up to the current row number.
   - The numbers are aligned to the right due to the spaces printed by the first inner loop.

4. **Right Alignment:**
   - The combination of spaces and numbers creates a right-aligned triangular pattern.

This program produces a triangle of numbers, with the numbers increasing in count and aligning to the right as the rows progress downward.
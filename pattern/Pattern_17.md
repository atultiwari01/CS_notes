# Pattern_17
```
        A
      A B
    A B C
  A B C D
A B C D E
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
            cout<<char('A'+col-1)<<" ";
        }
        cout<<endl;
    }
    return 0;
}
```
## Logic:
This program prints a right-aligned triangular pattern of uppercase letters (`A`, `B`, `C`, etc.). Each row contains letters starting from `A` and increasing up to the column number for that row. Here's the detailed explanation:

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
   - This loop prints spaces to align the letters to the right.
   - The condition `col <= 5 - row` ensures that the number of spaces decreases as the row number increases:
     - For `row = 1`, `5 - row = 4` → 4 spaces.
     - For `row = 2`, `5 - row = 3` → 3 spaces.
     - This continues until `row = 5`, where no spaces are printed.

3. **Second Inner Loop (Letters):**
   ```cpp
   for(int col = 1; col <= row; col++) {
       cout << char('A' + col - 1) << " ";
   }
   ```
   - This loop prints letters for the current row.
   - The condition `col <= row` ensures that the letters printed in each row go from `A` up to the `col`th letter:
     - `char('A' + col - 1)` calculates the character corresponding to the column number:
       - When `col = 1`, it prints `'A'`.
       - When `col = 2`, it prints `'B'`.
       - When `col = 3`, it prints `'C'`.
       - This continues as the row progresses.
     - For example:
       - For `row = 1`, the loop prints `A`.
       - For `row = 2`, the loop prints `A B`.
       - For `row = 3`, the loop prints `A B C`.

4. **Newline After Each Row:**
   ```cpp
   cout << endl;
   ```
   - After completing the loops for one row, a newline character is printed to move to the next row.

---

### Program Output

The output of the program will be:

```
        A
      A B
    A B C
  A B C D
A B C D E
```

---

### Key Points

1. **Outer Loop:**
   - Determines the row number and controls the execution of the inner loops.

2. **First Inner Loop (Spaces):**
   - Prints spaces to align the letters to the right.
   - The number of spaces decreases as the row number increases.

3. **Second Inner Loop (Letters):**
   - Prints letters starting from `A` up to the column number for the current row.
   - The ASCII value of `'A'` is used with `char('A' + col - 1)` to calculate the correct letter.

4. **Right Alignment:**
   - The combination of spaces and letters creates a right-aligned triangular pattern.

This program effectively combines ASCII arithmetic and nested loops to generate a triangular pattern of letters, aligned to the right.
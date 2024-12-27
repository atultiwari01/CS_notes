# Pattern_14
```
        *
      * *
    * * *
  * * * *
* * * * *
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
            cout<<" *";
        }
        cout<<endl;
    }
    return 0;
}
```
### Logic:
This program prints a right-angled triangular pattern of asterisks (`*`) aligned to the right side. Here's a detailed explanation of the logic:

---

### Code Breakdown

1. **Outer Loop (Row Loop):**
   ```cpp
   for(int row = 1; row <= 5; row++) {
   ```
   - The outer loop determines the number of rows in the pattern.
   - `row` starts at `1` and increments to `5`, creating 5 rows in total.

2. **First Inner Loop (Spaces):**
   ```cpp
   for(int col = 1; col <= 5 - row; col++) {
       cout << "  ";
   }
   ```
   - This loop prints spaces before the asterisks to align the pattern to the right.
   - The condition `col <= 5 - row` ensures that the number of spaces decreases as the row number increases:
     - For `row = 1`, `5 - row = 4` → 4 spaces.
     - For `row = 2`, `5 - row = 3` → 3 spaces.
     - This continues until `row = 5`, where no spaces are printed.

3. **Second Inner Loop (Asterisks):**
   ```cpp
   for(int col = 1; col <= row; col++) {
       cout << " *";
   }
   ```
   - This loop prints asterisks for the current row.
   - The condition `col <= row` ensures that the number of asterisks equals the current row number:
     - For `row = 1`, 1 asterisk is printed.
     - For `row = 2`, 2 asterisks are printed.
     - This continues until `row = 5`, where 5 asterisks are printed.

4. **Newline After Each Row:**
   ```cpp
   cout << endl;
   ```
   - After completing the loops for one row, a newline character is printed to move to the next row.

---

### Program Output

The output of the program will be:

```
        *
      * *
    * * *
  * * * *
* * * * *
```

---

### Key Points

1. **Outer Loop:**
   - Determines the number of rows in the pattern.
   - Controls the execution of the inner loops.

2. **First Inner Loop (Spaces):**
   - Prints spaces to shift the asterisks to the right.
   - The number of spaces decreases as the row number increases.

3. **Second Inner Loop (Asterisks):**
   - Prints the required number of asterisks for the current row.
   - The number of asterisks matches the row number.

4. **Right Alignment:**
   - The combination of the spaces and asterisks creates a right-aligned triangular pattern.

This is a simple way to create a triangular pattern with alignment using nested loops.
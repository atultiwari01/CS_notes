# Pattern_20

```
        1
      1 2 1
    1 2 3 2 1
  1 2 3 4 3 2 1
1 2 3 4 5 4 3 2 1
```
## Code:
```cpp
#include <iostream>
using namespace std;
int main(){
    for(int row = 1 ; row<=5 ; row++){
        for(int col = 1 ; col<=5-row ; col++){
            cout<<"  ";
        }
        for(int col = 1; col<=row ; col++){
            cout<<col<<" ";
        }
        for(int col = row-1; col>=1 ; col--){
            cout<<col<<" ";
        }
        cout<<endl;
    }
}
```
## Logic:
This program generates a pyramid pattern of numbers, with each row consisting of an increasing sequence of numbers followed by a decreasing sequence of numbers. Here’s a step-by-step explanation of the logic:

---

### 1. Outer Loop (`for(int row = 1; row <= 5; row++)`)
- **Purpose**: Controls the number of rows in the pyramid. 
- Iterates from `1` to `5`, where `row` represents the current row number.

---

### 2. First Inner Loop (`for(int col = 1; col <= 5 - row; col++)`)
- **Purpose**: Adds spaces before the numbers to align the pyramid symmetrically.
- The number of spaces decreases as the row number increases:
  - **Row 1**: \( 5 - 1 = 4 \) spaces
  - **Row 2**: \( 5 - 2 = 3 \) spaces
  - **Row 3**: \( 5 - 3 = 2 \) spaces
  - **Row 4**: \( 5 - 4 = 1 \) space
  - **Row 5**: \( 5 - 5 = 0 \) spaces
- Each space is represented by `"  "` (two spaces).

---

### 3. Second Inner Loop (`for(int col = 1; col <= row; col++)`)
- **Purpose**: Prints an **increasing sequence of numbers** starting from `1` and ending at the current row number (`row`).
- For example:
  - **Row 1**: \( 1 \)
  - **Row 2**: \( 1 \, 2 \)
  - **Row 3**: \( 1 \, 2 \, 3 \)
  - **Row 4**: \( 1 \, 2 \, 3 \, 4 \)
  - **Row 5**: \( 1 \, 2 \, 3 \, 4 \, 5 \)

---

### 4. Third Inner Loop (`for(int col = row - 1; col >= 1; col--)`)
- **Purpose**: Prints a **decreasing sequence of numbers** starting from `row - 1` down to `1`.
- For example:
  - **Row 1**: No numbers (since `row - 1 = 0`)
  - **Row 2**: \( 1 \)
  - **Row 3**: \( 2 \, 1 \)
  - **Row 4**: \( 3 \, 2 \, 1 \)
  - **Row 5**: \( 4 \, 3 \, 2 \, 1 \)

---

### 5. `cout << endl;`
- **Purpose**: Moves to the next line after completing a row, preparing to print the next row.

---

### Output
The program generates this pyramid pattern:

```
        1
      1 2 1
    1 2 3 2 1
  1 2 3 4 3 2 1
1 2 3 4 5 4 3 2 1
```

---

### Key Points:
1. **Spaces** ensure the pyramid shape.
2. The **second inner loop** handles the increasing sequence of numbers.
3. The **third inner loop** generates the decreasing sequence, creating the symmetric appearance.
4. The overall structure combines alignment (spaces) and symmetry (increasing and decreasing sequences).
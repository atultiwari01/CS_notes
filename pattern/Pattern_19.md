# Pattern_19
```
        *
      * * *
    * * * * *
  * * * * * * *
* * * * * * * * *
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
        for(int col = 1; col<=2*row-1 ; col++){
            cout<<" *";
        }
        cout<<endl;
    }
}
```
## Logic:
This program prints a pyramid pattern using nested loops. Here's a breakdown of the logic:

### Outer Loop (`for(int row = 1; row <= 5; row++)`)
- This loop iterates through each row of the pyramid (from 1 to 5).

### First Inner Loop (`for(int col = 1; col <= 5 - row; col++)`)
- This loop controls the spaces before the stars in each row.
- The number of spaces decreases as the row number increases:
  - **Row 1**: `5 - 1 = 4` spaces
  - **Row 2**: `5 - 2 = 3` spaces
  - **Row 3**: `5 - 3 = 2` spaces
  - **Row 4**: `5 - 4 = 1` space
  - **Row 5**: `5 - 5 = 0` spaces
- Each space is represented as `"  "` (two spaces).

### Second Inner Loop (`for(int col = 1; col <= 2 * row - 1; col++)`)
- This loop prints the stars (`*`) for each row.
- The number of stars follows the pattern \( 2 \times \text{row} - 1 \), which is:
  - **Row 1**: \( 2 \times 1 - 1 = 1 \) star
  - **Row 2**: \( 2 \times 2 - 1 = 3 \) stars
  - **Row 3**: \( 2 \times 3 - 1 = 5 \) stars
  - **Row 4**: \( 2 \times 4 - 1 = 7 \) stars
  - **Row 5**: \( 2 \times 5 - 1 = 9 \) stars
- Each star is preceded by a single space, `" *"`, to maintain symmetry.

### `cout << endl;`
- At the end of each row, this prints a newline, moving to the next row.

### Overall Output
The program generates a pyramid with 5 rows, aligned symmetrically, like this:

```
        *
      * * *
    * * * * *
  * * * * * * *
* * * * * * * * *
```


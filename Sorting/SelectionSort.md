# Selection Sort

## Code:

```cpp
#include <iostream>
using namespace std;

int main()
{
    int arr[6]= {5,6,9,7,2,1};
    
    for(int i=0;i<5;i++){
        int index=i;
        for(int j=i;j<6;j++)
        {
            if(arr[j]<arr[i])
            index = j;
        }
        swap(arr[i],arr[index]);
    }

    for(int i=0;i<6;i++){
        cout<<arr[i]<<" ";
    }
}
```
### **Algorithm Overview**

1. **Initialization**:
   - The array `arr[6]` is initialized with values `{5, 6, 9, 7, 2, 1}`.
   - The outer loop iterates through the array to place the smallest unsorted element at its correct position.

2. **Outer Loop** (`for(int i = 0; i < 5; i++)`):
   - Iterates over each position in the array except the last one, as the last element will already be sorted by the end.
   - `index` is initialized to the current position `i`. It represents the index of the smallest element found so far in the unsorted portion of the array.

3. **Inner Loop** (`for(int j = i; j < 6; j++)`):
   - Starts from the current position `i` and scans the remaining elements in the array.
   - If an element `arr[j]` is smaller than `arr[index]`, update `index` to `j`.

4. **Swapping**:
   - After the inner loop completes, `index` holds the position of the smallest element in the unsorted portion of the array.
   - Swap the smallest element (`arr[index]`) with the first element of the unsorted portion (`arr[i]`).

5. **Output**:
   - After sorting, the final array is printed in ascending order.

---

### **Step-by-Step Execution with Boxes Representation**

#### **Initial Array**:
```
[5] [6] [9] [7] [2] [1]
```

---

#### **Pass 1** (i = 0):
1. Start with the first element (`i = 0`).
2. Compare and find the smallest element from indices 0 to 5 (smallest = `1` at index 5).
3. Swap the smallest element (`1`) with the first element (`5`).

**After Swap**:
```
[1] [6] [9] [7] [2] [5]
```

---

#### **Pass 2** (i = 1):
1. Move to the second element (`i = 1`).
2. Compare and find the smallest element from indices 1 to 5 (smallest = `2` at index 4).
3. Swap the smallest element (`2`) with the second element (`6`).

**After Swap**:
```
[1] [2] [9] [7] [6] [5]
```

---

#### **Pass 3** (i = 2):
1. Move to the third element (`i = 2`).
2. Compare and find the smallest element from indices 2 to 5 (smallest = `5` at index 5).
3. Swap the smallest element (`5`) with the third element (`9`).

**After Swap**:
```
[1] [2] [5] [7] [6] [9]
```

---

#### **Pass 4** (i = 3):
1. Move to the fourth element (`i = 3`).
2. Compare and find the smallest element from indices 3 to 5 (smallest = `6` at index 4).
3. Swap the smallest element (`6`) with the fourth element (`7`).

**After Swap**:
```
[1] [2] [5] [6] [7] [9]
```

---

#### **Pass 5** (i = 4):
1. Move to the fifth element (`i = 4`).
2. Compare and find the smallest element from indices 4 to 5 (smallest = `7` at index 4). No swap needed.

**Final Array**:
```
[1] [2] [5] [6] [7] [9]
```

---

### **Final Visualization of Each Step**:

- **Initial**: `[5] [6] [9] [7] [2] [1]`
- **Pass 1**: `[1] [6] [9] [7] [2] [5]`
- **Pass 2**: `[1] [2] [9] [7] [6] [5]`
- **Pass 3**: `[1] [2] [5] [7] [6] [9]`
- **Pass 4**: `[1] [2] [5] [6] [7] [9]`
- **Pass 5**: `[1] [2] [5] [6] [7] [9]`

---

### **Key Points**

- **Time Complexity**: \(O(n^2)\) in the worst case because of the nested loops.
- **Space Complexity**: \(O(1)\) as it sorts the array in place.
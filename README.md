# L-and-D-Assignment-
Name : Nutan    (2232143)     cse A   (L and D )




1. Insert an Element in an Array (C++)
 Algorithm:
1. Input the array size, the array elements, the element to insert, and the position.
2. Shift elements to the right starting from the insertion point.
3. Insert the new element at the specified position.
4. Output the updated array.
 Code:

#include <iostream>
using namespace std;

void insertElement(int arr[], int &n, int element, int position) {
    // Shift elements to the right
    for (int i = n; i > position; i--) {
        arr[i] = arr[i - 1];
    }
    arr[position] = element;
    n++;
}

int main() {
    int arr[100] = {1, 2, 4, 5};
    int n = 4;  // Current number of elements
    int element = 3, position = 2;

    insertElement(arr, n, element, position);

    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}

2. Delete an Element from an Array (C++)
Algorithm:
1. Input the array size, the array elements, and the position of the element to delete.
2. Shift elements to the left from the deletion point.
3. Decrease the array size by 1.
4. Output the updated array.

Code:
cpp
#include <iostream>
using namespace std;

void deleteElement(int arr[], int &n, int position) {
    // Shift elements to the left
    for (int i = position; i < n - 1; i++) {
        arr[i] = arr[i + 1];
    }
    n--;  // Decrease size
}

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    int n = 5;
    int position = 2;

    deleteElement(arr, n, position);

    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}

 3. Find the Maximum and Minimum Element in an Array (C++)
Algorithm:
1. Input the array size and the elements.
2. Initialize variables for max and min with the first element.
3. Iterate through the array, updating the max and min values.
4. Output the max and min values.

 Code:
#include <iostream>
using namespace std;

void findMaxMin(int arr[], int n, int &max_val, int &min_val) {
    max_val = min_val = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] > max_val)
            max_val = arr[i];
        if (arr[i] < min_val)
            min_val = arr[i];
    }
}

int main() {
    int arr[] = {3, 1, 9, 4, 6};
    int n = 5;
    int max_val, min_val;

    findMaxMin(arr, n, max_val, min_val);

    cout << "Max: " << max_val << ", Min: " << min_val << endl;
    return 0;
}

 4. Reverse an Array (C++)
 Algorithm:
1. Input the array size and the elements.
2. Initialize two pointers: one at the start and the other at the end.
3. Swap the elements at the pointers and move them towards each other.
4. Output the reversed array.

Code:
#include <iostream>
using namespace std;

void reverseArray(int arr[], int n) {
    int start = 0, end = n - 1;
    while (start < end) {
        swap(arr[start], arr[end]);
        start++;
        end--;
    }
}

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    int n = 5;

    reverseArray(arr, n);

    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}
5. Find the Second Largest Element in an Array (C++)
Algorithm:
1. Input the array size and the elements.
2. Initialize two variables `first` and `second` for storing the largest and second largest values.
3. Traverse the array, updating `first` and `second` accordingly.
4. Output the second largest value.
 Code:

#include <iostream>
using namespace std;

int findSecondLargest(int arr[], int n) {
    if (n < 2) {
        return -1;  // Error case: Less than two elements
    }

    int first = INT_MIN, second = INT_MIN;
    
    for (int i = 0; i < n; i++) {
        if (arr[i] > first) {
            second = first;
            first = arr[i];
        } else if (arr[i] > second && arr[i] != first) {
            second = arr[i];
        }
    }

    return (second == INT_MIN) ? -1 : second;  // In case all elements are the same
}

int main() {
    int arr[] = {12, 35, 1, 10, 34, 1};
    int n = 6;

    int secondLargest = findSecondLargest(arr, n);
    if (secondLargest == -1)
        cout << "There is no second largest element" << endl;
    else
        cout << "The second largest element is " << secondLargest << endl;

    return 0;
}

7. Create a 2D Array (C++)
Algorithm:
1. Input the number of rows and columns.
2. Dynamically allocate memory for a 2D array using nested loops.
3. Input the elements of the 2D array.
4. Output the 2D array.

Code:
cpp
#include <iostream>
using namespace std;

void create2DArray(int rows, int cols) {
    // Create a 2D array
    int arr[100][100];

    // Input elements
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << "Enter element [" << i << "][" << j << "]: ";
            cin >> arr[i][j];
        }
    }

    // Output the 2D array
    cout << "2D Array:" << endl;
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << arr[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int rows = 3, cols = 3;
    create2DArray(rows, cols);
    return 0;
}

8. Matrix Addition, Multiplication, and Transpose (C++)

#Matrix Addition
Algorithm:
1. Input two matrices.
2. Add corresponding elements of both matrices.
3. Output the resulting matrix.
Code:
cpp
#include <iostream>
using namespace std;

void matrixAddition(int A[][3], int B[][3], int rows, int cols) {
    int result[3][3];
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            result[i][j] = A[i][j] + B[i][j];
        }
    }

    cout << "Matrix Addition Result:" << endl;
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << result[i][j] << " ";
        }
        cout << endl;
    }

Matrix Multiplication
Algorithm:
1. Input two matrices.
2. Multiply corresponding elements by using the dot product of rows and columns.
3. Output the resulting matrix.

 Code:
cpp
void matrixMultiplication(int A[][3], int B[][3], int rows, int cols) {
    int result[3][3] = {0};
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            for (int k = 0; k < cols; k++) {
                result[i][j] += A[i][k] * B[k][j];
            }
        }
    }

    cout << "Matrix Multiplication Result:" << endl;
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << result[i][j] << " ";
        }
        cout << endl;
    }
}
Matrix Transpose
Algorithm:
1. Input a matrix.
2. Swap rows with columns.
3. Output the transposed matrix.
Code:
cpp
void matrixTranspose(int A[][3], int rows, int cols) {
    int result[3][3];
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            result[j][i] = A[i][j];
        }
    }

    cout << "Matrix Transpose Result:" << endl;
    for (int i = 0; i < cols; i++) {
        for (int j = 0; j < rows; j++) {
            cout << result[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int A[3][3] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
    int B[3][3] = {{9, 8, 7}, {6, 5, 4}, {3, 2, 1}};
    int rows = 3, cols = 3;

    matrixAddition(A, B, rows, cols);
    matrixMultiplication(A, B, rows, cols);
    matrixTranspose(A, rows, cols);

    return 0;
}

9. Two Sum Problem (C++)
Algorithm:
1. Create a map to store the difference between the target and current element, and store the index of the element.
2. Traverse the array, for each element:
   - Calculate the complement (target - element).
   - If the complement exists in the map, return the indices of the complement and the current element.
3. If no pair is found, return an error.
Code:
#include <iostream>
#include <unordered_map>
#include <vector>
using namespace std;

vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int, int> map;  // Stores the value and its index
    for (int i = 0; i < nums.size(); i++) {
        int complement = target - nums[i];
        if (map.find(complement) != map.end()) {
            return {map[complement], i};
        }
        map[nums[i]] = i;  // Store index of the current number
    }
    return {};  // Return empty if no pair is found
}

int main() {
    vector<int> nums = {2, 7, 11, 15};
    int target = 9;
    
    vector<int> result = twoSum(nums, target);
    
    if (!result.empty()) {
        cout << "Indices: " << result[0] << ", " << result[1] << endl;
    } else {
        cout << "No two numbers add up to the target." << endl;
    }
    
    return 0;
}

10. Segregate Even and Odd Numbers in an Array (C++)
Algorithm:
1. Input the array.
2. Create two separate lists: one for even numbers and another for odd numbers.
3. Traverse the array, appending even numbers to the even list and odd numbers to the odd list while maintaining their relative order.
4. Concatenate the even list followed by the odd list.
5. Output the rearranged array.
Code:
cpp
#include <iostream>
#include <vector>
using namespace std;

vector<int> segregateEvenOdd(vector<int>& arr) {
    vector<int> even, odd;

    // Traverse the array and segregate even and odd numbers
    for (int num : arr) {
        if (num % 2 == 0) {
            even.push_back(num);
        } else {
            odd.push_back(num);
        }
    }

    // Concatenate even and odd arrays
    even.insert(even.end(), odd.begin(), odd.end());
    return even;
}

int main() {
    vector<int> arr = {12, 34, 45, 9, 8, 90, 3};

    vector<int> result = segregateEvenOdd(arr);

    cout << "Segregated Array: ";
    for (int num : result) {
        cout << num << " ";
    }
    cout << endl;

    return 0;
}

 Explanation:
Step 1:Create two vectors: one to store even numbers and another to store odd numbers.
Step 2: Loop through the input array, checking each number to determine whether it is even or odd. Store the even numbers in the `even` vector and the odd numbers in the `odd` vector.
Step 3:After processing the entire array, concatenate the `even` vector followed by the `odd` vector, preserving their relative order.
Step 4:Output the combined result.
Example:
Input:
arr = [12, 34, 45, 9, 8, 90, 3]
Output:
Segregated Array: 12 34 8 90 45 9 3
The even numbers come first, followed by the odd numbers, while maintaining their original relative order.

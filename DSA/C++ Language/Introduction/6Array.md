







#### `arr[i]` and `i[arr]` are equivalent and mean the same thing.


```
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int i = 2;

    cout << arr[i] << endl; // Output: 30
    cout << i[arr] << endl; // Output: 30

    return 0;
}

```
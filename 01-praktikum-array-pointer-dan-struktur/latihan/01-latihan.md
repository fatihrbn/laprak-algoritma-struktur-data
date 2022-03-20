# Latihan 1

Terdapat array dengan tipe char yang berisi ```{'p', 'e', 'n', 's', 'i', 't'}```, baliklah array tersebut menjadi tisnep.

## Code
```c
#include <iostream>
using namespace std;

int main() {
  char arr[] = {'p', 'e', 'n', 's', 'i', 't'};
  int arrSize = sizeof(arr)/sizeof(arr[0]);
  int left = 0;
  int right = arrSize - 1;

  while (left < right) {
    int temp = arr[left];
    arr[left] = arr[right];
    arr[right] = temp;
    left++;
    right--;
  }

  for (int i = 0; i < arrSize; i++) {
    cout << arr[i];
  }
  return 0;
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159176284-74f88833-2105-4850-9719-940a564afd00.png)

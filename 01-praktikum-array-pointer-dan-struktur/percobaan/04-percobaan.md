# Percobaan 4 : Cara mengakses array dua dimensi

## Code
``` c
#include <iostream>
using namespace std;

int main () {
  int a[5][2] = { {0,0}, {1,2}, {2,4}, {3,6},{4,8}};
  int i, j;
  for ( i = 0; i < 5; i++ ) {
    for ( j = 0; j < 2; j++ ) {
      cout << "a[" << i << "][" << j << "] = " << a[i][j] << endl;
    }
  }

  return 0;
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159174807-af6a8898-4f33-4cc7-bc5d-f39791114d35.png)

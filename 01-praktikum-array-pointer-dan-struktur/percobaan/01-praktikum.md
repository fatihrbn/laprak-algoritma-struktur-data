# 01-praktikum: Cara memberikan nilai pada array dan mengakses array

## Code
``` c
#include <iostream>
using namespace std;

int main () {
  int i, j, n[10];
  for ( i = 0; i < 10; i++ ) {
    n[i] = i + 100;
  }
  for (j = 0; j < 10; j++ ) {
    cout << "Element[" << j << "] = " << n[j] << endl;
  }
  return 0;
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159174393-03e2dded-8341-438d-9c2d-6ead39bd86d8.png)


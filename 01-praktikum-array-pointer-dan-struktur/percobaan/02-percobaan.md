# Percobaan 2 : Menghitung total dari nilai yang terdapat pada array

## Code
``` c
#include <iostream>
using namespace std;

#define SIZE 12

int main () {
  int a[SIZE] = { 1, 3, 5, 4, 7, 2, 99,16, 45, 67, 89, 45 };
  int i = 0;
  int total = 0;
  for(i = 0; i<SIZE; ++i) {
    total+=a[i];
  }
  cout << "Total elemen yang terdapat di array : " << total << endl;

  return 0;
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159174596-2e2176c2-311c-4a17-b287-b0b714c82711.png)

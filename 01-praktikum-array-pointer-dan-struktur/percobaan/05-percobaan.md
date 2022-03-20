# Percobaan 5 : Program Merubah Isi Variabel melalui Pointer

## Code
``` c
#include <iostream>
using namespace std;

int main () {
  int y, x = 87;
  int *px;
  x = 87;
  px = &x; 
  y = *px;
  cout << "Alamat x = " << &x << endl;
  cout << "Isi px = " << px << endl;
  cout << "Isi x = " << x << endl;
  cout << "Nilai yang ditunjuk oleh px = " << *px << endl;
  cout << "Nilai y = " << y << endl;

  return 0;
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159174857-094479a0-6572-46dd-81f9-3a8fbbd7fece.png)

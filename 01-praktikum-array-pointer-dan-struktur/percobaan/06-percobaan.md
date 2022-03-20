# Percobaan 6 : Program Mengakses & Mengubah Isi Suatu Variabel Pointer

## Code
``` c
#include <iostream>
using namespace std;

int main () {
  float d = 54.5f, *pd;
  cout << "Isi d mula-mula = " << d << endl;
  pd = &d;
  *pd += 10;
  cout << "Isi d sekarang = " << d << endl;

  return 0;
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159174916-7d0f01a0-df41-4695-ad40-099c81b7fd62.png)

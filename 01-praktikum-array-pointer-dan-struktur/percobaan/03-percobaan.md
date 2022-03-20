# Percobaan 3 : Penggunaan Array pada Bilangan Fibonaci

## Code
``` c
#include <iostream>
using namespace std;
#define MAX 20
int fibo[MAX];

int main () {
  int i;
  fibo[1] = 1;
  fibo[2] = 1;
  for (i=3;i<=MAX;i++) {
    fibo[i]=fibo[i-2]+fibo[i-1];
  }
  cout << MAX << " Bilangan Fibonaci Pertama adalah : " << endl;
  for (i=1;i<MAX;i++) {
    cout << fibo[i] << " ";
  }
  return 0;
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159174735-01e88b8c-3d46-44c1-91f6-38821847ad7e.png)

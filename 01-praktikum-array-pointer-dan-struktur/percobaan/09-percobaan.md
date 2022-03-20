# Percobaan 9 : Penggunaan Pointer untuk Bilangan Fibonaci

## Code
``` c
#include<iostream>
#include<cstdlib>
using namespace std;

#define MAX 20

int main() {
  int *fibo;
  int i;

  fibo = (int *) malloc(MAX * sizeof(int*));
  *(fibo + 1) = 1;
  *(fibo + 2) = 1;

  for (i=3;i<=MAX;i++) {
    *(fibo + i) = (*(fibo + i - 2) + *(fibo + i - 1));
  }
  cout << MAX << " Bilangan Fibonaci Pertama adalah : \n";
  for (i=1;i<MAX;i++) {
    cout << *(fibo+i) << " ";
  }
}
```

# Output
![image](https://user-images.githubusercontent.com/89684302/159175069-7be92ed0-8c7e-47c7-980f-82a8ecf2cc29.png)

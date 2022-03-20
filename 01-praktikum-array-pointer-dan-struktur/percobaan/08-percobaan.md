# Percobaan 8 : Mengkopi string menggunakan pointer.

## Code
``` c
#include <iostream>
using namespace std;

char strA[80] = "ABCDE";
char strB[80];

int main() {
  char *pA;
  char *pB;

  cout << strA << endl;
  pA = strA;
  cout << pA << endl << endl;
  pB = strB;
  while(*pA != '\0') {
    *pB++ = *pA++;
  }
  *pB = '\0';
  cout << strB << endl;
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159175026-48b38703-5ebb-49ec-9dfa-8900e1ac3a2c.png)

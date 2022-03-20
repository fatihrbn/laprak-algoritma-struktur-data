# Latihan 3

Bagaimana output program di bawah ini ?

## Code
```c
#include <iostream>
using namespace std;

int main() {
  int count = 10, sum = 7, *temp;

  temp = &count;
  temp = &count;
  *temp = 32;
  temp = &sum;
  *temp = count;
  sum = *temp * 4;

  cout << "count=" << count << ", *temp=" << *temp << ", sum=" << sum;
  return 0;
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159176438-577021c3-abe8-40a7-8228-c1f6a981516e.png)

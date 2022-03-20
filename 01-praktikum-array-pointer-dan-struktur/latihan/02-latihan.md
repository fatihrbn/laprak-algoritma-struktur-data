# Latihan 2

Terdapat dua buah matrik dengan ordo n yang direpresentasikan dengan array dimensi dua, lakukan operasi penjumlahan, pengurangan dan perkalian.

## Code
```c
#include <iostream>
using namespace std;
#define N 2

void penjumlahanMatriks(int a[N][N], int b[N][N]) {
  int sum[N][N];
  for (int i = 0; i < N; i++) {
    for (int j = 0; j < N; j++) {
      sum[i][j] = a[i][j] + b[i][j];
      cout << sum[i][j] << " ";
    }
    cout << endl;
  }
}

void penguranganMatriks(int a[N][N], int b[N][N]) {
  int sum[N][N];
  for (int i = 0; i < N; i++) {
    for (int j = 0; j < N; j++) {
      sum[i][j] = a[i][j] - b[i][j];
      cout << sum[i][j] << " ";
    }
    cout << endl;
  }
}

void perkalianMatriks(int a[N][N], int b[N][N]) {
  int sum[N][N];
  for (int i = 0; i < N; i++) {
    for (int j = 0; j < N; j++) {
      sum[i][j] = 0;

      for (int k = 0; k < N; k++) {
        sum[i][j] += a[i][k] * b[k][j];
      }
      cout << sum[i][j] << " ";
    }
    cout << endl;
  }
}

void inputMatriks(int a[N][N], char name) {
  cout << "Matriks " << name << ":" << endl;
  for (int i = 0; i < N; i++) {
    for (int j = 0; j < N; j++) {
      cin >> a[i][j];
    }
  }
}

int main() {
  int arr1[N][N], arr2[N][N];

  inputMatriks(arr1, 'A');
  inputMatriks(arr2, 'B');

  cout << "Hasil penjumlahan:" << endl;
  penjumlahanMatriks(arr1, arr2);
  cout << "Hasil pengurangan:" << endl;
  penguranganMatriks(arr1, arr2);
  cout << "Hasil perkalian:" << endl;
  perkalianMatriks(arr1, arr2);

  return 0;
}
```
## Output
![image](https://user-images.githubusercontent.com/89684302/159176372-b5c68cae-7a35-47ef-929e-7d0a2e7d7510.png)

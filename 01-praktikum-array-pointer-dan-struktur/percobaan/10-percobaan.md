# Percobaan 10 : Penggunaan Struktur pada Konversi Koordinat Polar ke Koordinat Cartesian

## Code
``` c
#include <stdio.h>
#include <math.h>

struct polar {
  double r;
  double alpha;
};

struct kartesian {
  double x;
  double y;
};

int main() {
  struct polar p1;
  struct kartesian k1;

  printf("Masukkan nilai r untuk koordinat polar : ");
  scanf("%lf",&p1.r);
  printf("Masukkan nilai alpha untuk koordinat polar : ");
  scanf("%lf",&p1.alpha);
  k1.x = p1.r * cos(p1.alpha);
  k1.y = p1.r * sin(p1.alpha);
  printf("Nilai koordinat kartesian untuk koordinat polar r= %2.2lf alpha= %2.2lf adalah:\n",p1.r,p1.alpha);
  printf("x = %2.2lf y = %2.2lf",k1.x,k1.y);
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159175127-a19a534f-0b65-4bee-a4ff-703682fda435.png)

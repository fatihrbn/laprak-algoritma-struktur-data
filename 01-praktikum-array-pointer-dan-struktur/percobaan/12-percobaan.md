# Percobaan 12 : Mengakses Struktur dengan Pointer

## Code
``` c
#include <stdio.h>
#include <string.h>

  struct dtnilai {
    char nrp[10];
    char nama[20];
    double nilai;
  };
  struct dtnilai my_struct;

void tampil(struct dtnilai *p)
{
  printf("\n%s ", p->nrp);
  printf("%s ", p->nama);
  printf("%6.2lf", p->nilai);
}

int main() {
  struct dtnilai *st_ptr; 
  st_ptr = &my_struct;
  strcpy(my_struct.nrp,"01");
  printf("\n%s ",my_struct.nrp);
  strcpy(my_struct.nama,"Arini");
  printf("\n%s ",my_struct.nama);
  my_struct.nilai = 63.6;
  tampil(st_ptr);
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159175319-d2c4e46b-9205-4f43-943d-0e694beefd26.png)

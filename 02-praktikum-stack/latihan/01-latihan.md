# Latihan 1
Lakukan operasi berikut :

• Jika karakter maka push ke stack

• Jika asterisk (*) maka pop dan cetak hasilnya.

Bagaimana output program dengan input seperti di bawah ini ?

E A S * Y * Q U E * * * S T * * * I O * N * * *

## Code 
``` c
//latihan1.c
#include <stdio.h>
#include <string.h>
#define MAX 50

typedef char ItemType;
typedef struct {
  ItemType item[MAX];
  int count;
} Stack;

void initializeStack(Stack *S) {
  S->count = 0;
}

int isEmpty(Stack *S) {
  return (S->count == 0);
}

int isFull(Stack *S) {
  return (S->count == MAX);
}

void push(Stack *S, ItemType x) {
  if (isFull(S)) {
    printf("Stack penuh, Data tidak dapat disimpan\n");
  } else {
    S->item[S->count] = x;
    S->count++;
  }
}

void pop(Stack *S) {
  ItemType temp;
  if (isEmpty(S)) {
    printf("Stack kosong, tidak dapat mengambil data\n");
  } else {
    S->count--;
    temp = S->item[S->count];
    printf("%c", temp);
  }
}

int main() {
  char word[] = "E A S * Y * Q U E * * * S T * * * I O * N * * *";
  int wordLength = strlen(word);
  Stack stack;
  initializeStack(&stack);
  printf("Input:\n");
  printf("%s\n\n", word);
  printf("Output:\n");
  for (int i = 0; i < wordLength; i++) {
    if (word[i] == '*') {
      pop(&stack);
    } else if (word[i] == ' ') {
      continue;
    } else {
      push(&stack, word[i]);
    }
  }
  return 0;
}
```

## Penjelasan
```c
int main() {
  char word[] = "E A S * Y * Q U E * * * S T * * * I O * N * * *";
  int wordLength = strlen(word);
  Stack stack;
  initializeStack(&stack);
  for (int i = 0; i < wordLength; i++) {
    if (word[i] == '*') {
      pop(&stack);
    } else if (word[i] == ' ') {
      continue;
    } else {
      push(&stack, word[i]);
    }
  }
  return 0;
}
```
Menggunakan ```for``` loop pada array ```word``` untuk mengakses tiap karakter pada array. Kemudian menggunakan ```if else``` atau conditional statement untuk melakukan operasi stack. Jika karakter pada index ke-i nilainya sama dengan asterix(\*), maka ```pop``` dan cetak karakter pada stack. Jika karakter pada index ke-i nilainya sama dengan spasi(' '), maka lanjutkan looping ke index berikutnya. Jika karakter pada index ke-i nilainya tidk sama dengan asterix dan spasi, maka ```push``` karakter tersebut ke dalam stack.
## Output
![image](https://user-images.githubusercontent.com/89684302/159175707-296be16e-abab-4961-8fc1-735bbd03241c.png)

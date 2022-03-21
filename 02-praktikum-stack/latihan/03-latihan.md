# Latihan 3

Buatlah sebuah program yang melakukan pembalikan terhadap kalimat dengan menggunakan stack

Contoh:

Kalimat : Struktur Data

Hasil setelah dibalik : ataD rutkurtS

## Code
``` c
//latihan3.c
#include <stdio.h>
#include <string.h>
#define MAX 50

typedef char ItemType;
typedef struct {
  ItemType item[MAX];
  int count;
} Stack;

Stack stack;

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

void reverseWord(char word[]) {
  char temp;
  int wordLength = strlen(word);
  for (int i = 0; i < wordLength; i++) {
    temp = word[i];
    push(&stack, temp);
  }
  for (int j = 0; j < wordLength; j++) {
    pop(&stack);
  }
}

int main() {
  char str[] = "Struktur Data";
  initializeStack(&stack);

  printf("Kalimat : \n");
  printf("%s\n\n", str);
  printf("Hasil setelah dibalik : \n");
  reverseWord(str);
  return 0;
}
```

## Penjelasan
```c
void reverseWord(char word[]) {
  char temp;
  int wordLength = strlen(word);
  for (int i = 0; i < wordLength; i++) {
    temp = word[i];
    push(&stack, temp);
  }
  for (int j = 0; j < wordLength; j++) {
    pop(&stack);
  }
}
```
Menggunakan fungsi ```reverseWord(char word[])``` untuk membalikkan kalimat. Menggunakan ```for``` loop untuk mengakses elemen pada tiap index array ```word``` dan melakukan operasi ```push``` ke dalam stack. Kemudian membuat ```for``` loop yang baru untuk melakukan operasi ```pop``` pada stack dan mencetaknya ke tampilan console. Dengan menggunakan konsep LIFO (Last In First Out), maka tiap elemen pada array ```word``` akan dicetak secara terbalik pada tampilan console.

## Output
![image](https://user-images.githubusercontent.com/89684302/159175923-773370a1-1dac-4cf2-bfc0-608cf9aca235.png)

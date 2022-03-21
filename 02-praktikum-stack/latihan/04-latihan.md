# Latihan 4

Tentukan apakah sebuah kalimat yang diinputkan dalam program (dengan menggunakan stack) adalah sebuah palindrom atau bukan. Palindrom adalah kalimat yang jika dibaca dari depan dan dari belakang, maka bunyinya sama.

Contoh:

Kalimat : sugus

Kalimat tersebut adalah palindrom

## Code
```c
//latihan4.c
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

char pop(Stack *S) {
  ItemType temp;
  if (isEmpty(S)) {
    printf("Stack kosong, tidak dapat mengambil data\n");
    return 0;
  } else {
    S->count--;
    return temp = S->item[S->count];
  }
}

void reverseWordCompare(char word[]) {
  int wordLength = strlen(word);
  char temp, reverseWord[wordLength];
  for (int i = 0; i < wordLength; i++) {
    temp = word[i];
    push(&stack, temp);
  }
  for (int j = 0; j < wordLength; j++) {
    reverseWord[j] = pop(&stack);
  }
  printf("%s\n\n", reverseWord);

  if (strcmp(word, reverseWord) == 0) {
    printf("Kalimat tersebut palindrome");
  } else {
    printf("Kalimat tersebut tidak palindrome");
  }
}

int main() {
  char str[] = "kasur ini rusak";
  initializeStack(&stack);

  printf("Kalimat : \n");
  printf("%s\n\n", str);
  printf("Hasil setelah dibalik : \n");
  reverseWordCompare(str);

  return 0;
}
```

## Penjelasan
```c
void reverseWordCompare(char word[]) {
  int wordLength = strlen(word);
  char temp, reverseWord[wordLength];
  for (int i = 0; i < wordLength; i++) {
    temp = word[i];
    push(&stack, temp);
  }
  for (int j = 0; j < wordLength; j++) {
    reverseWord[j] = pop(&stack);
  }
  printf("%s\n\n", reverseWord);

  if (strcmp(word, reverseWord) == 0) {
    printf("Kalimat tersebut palindrome");
  } else {
    printf("Kalimat tersebut tidak palindrome");
  }
}
```
Menyimpan hasil dari kalimat yang sudah dibalik ke dalam variabel ```reverseWord```, kemudian menggunakan fungsi ```strcmp()``` dari library ```<string.h>``` untuk membandingkan variabel ```word``` dan ``reverseWord```. Jika hasil perbandingan menghasilkan nilai 0, maka kedua variabel tersebut sama. Jika hasilnya tidak sama dengan 0, maka kedua variabel tersebut tidak sama.
## Output
![image](https://user-images.githubusercontent.com/89684302/159176050-e66ada8e-6f0e-4080-88c9-c99b3245b4a9.png)

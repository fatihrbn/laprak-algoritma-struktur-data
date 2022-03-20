# Latihan 2

Buatlah sebuah program yang melakukan konversi dari bilangan desimal ke
bilangan biner, octal, heksa dengan menggunakan stack

## Code
``` c
#include <stdio.h>
#include <string.h>
#define MAX 50

typedef int ItemType;
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

int pop(Stack *S) {
  ItemType temp;
  if (isEmpty(S)) {
    printf("Stack kosong, tidak dapat mengambil data\n");
    return 0;
  } else {
    S->count--;
    temp = S->item[S->count];
    return temp;
  }
}

void decimalToBinary(Stack *S, ItemType n) {
  while (n != 0) {
    push(S, n%2);
    n /= 2;
  }
  printf("Binary : ");
  while (S->count > 0) {
    printf("%d",pop(S));
  }
}

void decimalToOctal(Stack *S, ItemType n) {
  while (n != 0) {
    push(S, n%8);
    n /= 8;
  }
  printf("Octal : ");
  while (S->count > 0) {
    printf("%d",pop(S));
  }
}

void decimalToHexadecimal(Stack *S, ItemType n) {
  int hexResult;
  while (n != 0) {
    push(S, n%16);
    n /= 16;
  }
  printf("Hexadecimal : ");
  while (S->count > 0) {
    hexResult = pop(S);
    switch(hexResult) {
      case 10:
        hexResult = 'A';
        printf("%c", hexResult);
        break;
      case 11:
        hexResult = 'B';
        printf("%c", hexResult);
        break;
      case 12:
        hexResult = 'C';
        printf("%c", hexResult);
        break;
      case 13:
        hexResult = 'D';
        printf("%c", hexResult);
        break;
      case 14:
        hexResult = 'E';
        printf("%c", hexResult);
        break;
      case 15:
        hexResult = 'F';
        printf("%c", hexResult);
        break;
      default:
        printf("%d", hexResult);
    }
  }
}

int main() {
  ItemType number = 123;
  Stack stack;
  initializeStack(&stack);
  printf("Decimal number: %d\n", number);
  decimalToBinary(&stack, number);
  printf("\n");
  decimalToOctal(&stack, number);
  printf("\n");
  decimalToHexadecimal(&stack, number);
  return 0;
}
```

## Output
![image](https://user-images.githubusercontent.com/89684302/159175771-b1caeaa0-e220-4597-8d4c-8c5f32d720dd.png)

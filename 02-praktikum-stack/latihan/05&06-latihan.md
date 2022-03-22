# Latihan 5
Tambahkan implementasi Percobaan2 untuk mengecek apakah notasi infix yang diinputkan benar atau tidak.<br>
Contoh :<br>
Infix : 5 * ( 4 – 2 <br>
Output : Notasi infix salah, kurung tidak lengkap<br>
Infix : 5 * ( 4 – )<br>
Output : Notasi infix salah, operand tidak lengkap<br>
Infix : 5 ( 4 – 2 )<br>

# Latihan 6
Tambahkan implementasi Percobaan2 hingga mendapatkan hasil penghitungannya.<br>
Contoh:<br>
infix : 5 \* ( 4 – 2 )<br>
postfix : 542-\*<br>
hasil : 10<br>

## Code 
```c
//prak2lat56.cpp
#include <stdio.h>
#include <string.h>
#include<bits/stdc++.h>
#include<iostream>
#include<math.h>
#define MAXSTACK 100
using namespace std;
typedef char ItemType;
typedef struct {
  char item[MAXSTACK]; /* Array yg berisi data tumpukan */
  int count; /* menunjukkan indeks data paling atas dari stack*/
} Stack;
Stack tumpukan;
void InitializeStack(Stack *);
int Empty(Stack *);
int Full(Stack *);
void Push(ItemType, Stack *);
ItemType Pop(Stack *);
int drjt(char);
void konversi_cetak(char []);

int main() {
  char tampung[MAXSTACK], jawab;
  do {
    InitializeStack(&tumpukan);
    fflush(stdin);
    puts("");
    puts("mohon tidak memakai spasi");
    printf("infix : ");
    fgets(tampung, sizeof(tampung), stdin);
    printf("Postfix : ");
    konversi_cetak(tampung);
    puts("");
    fflush(stdin);
    printf("\nMau mencoba lagi (y/t) ? ");
    scanf("%c", &jawab);
  } while((jawab == 'y') || (jawab == 'Y'));
}

void InitializeStack(Stack *S) {
  S->count = 0;
}

int Empty(Stack *S) {
  return (S->count == 0);
}

int Full(Stack *S) {
  return (S->count == MAXSTACK);
}

void Push(ItemType x, Stack *S) {
  if (Full(S)) //stack penuh
    printf("Stack penuh! Data tidak dapat masuk!");
  else {
    ++(S->count);
    S->item[S->count]=x;
  }
}

ItemType Pop(Stack *S) {
  ItemType x;
  if (Empty(S)) { //stack kosong
    printf ("STACK KOSONG!");
    return 0;
  } else {
    x = (S->item[S->count]);
    --(S->count);
    return x;
  }
}

int drjt(char x) { //menentukan derajat operator
  if(x == '(')
    return 0;
  else if((x == '+') || (x == '-'))
    return 1;
  else if((x == '*') || (x == '/'))
    return 2;
  else if(x == '^')
    return 3;
  else
    return -1;
}


void konversi_cetak(char temp[]) {
  int i,h=0, j=0, l=0, m=0, pjg, valid = 1;
  char kar, smtr;
  pjg = strlen(temp)-1;
  for (i=0; i<pjg; i++) {
    kar = temp[i]; //membaca input per karakter
    switch(kar) {
//if kar = '(' -> push ke dalam tumpukan
      case '(' :
        Push(kar, &tumpukan);
        h++;
        break;
//if kar = operand -> langsung ditulis
      case '0': case '1': case '2': case '3': case '4':
      case '5': case '6': case '7': case '8': case '9':
        j++;
        printf("%c", kar);
        break;
      case '+': case '-': case'*': case '/': case '^':
        l++;
        if((Empty(&tumpukan)) || ((drjt(kar) > drjt(tumpukan.item[tumpukan.count]))))
          Push(kar, &tumpukan);
        else {
          do {
            smtr = Pop(&tumpukan);
            printf("%c", smtr);
          } while (drjt(kar) <
                   drjt(tumpukan.item[tumpukan.count]));
          Push(kar, &tumpukan);
        }
        break;
      case ')' :
        m++;
        while(tumpukan.item[tumpukan.count] != '(') {
          smtr = Pop(&tumpukan);
          printf("%c", smtr);
        }
        Pop(&tumpukan);
        break;
      default : //selain dari kar yang diijinkan
        valid = 0;
        printf("SPASI");
        break;
    }
  }
  if((valid != 0) && (!Empty(&tumpukan))) {
    smtr = Pop(&tumpukan);
    printf("%c", smtr);
  }
  if(h!=m) {
    printf("\nOutput : Notasi infix salah, kurung tidak lengkap");
  } else if(j==l) {
    printf("\nOutput : Notasi infix salah, operand tidak lengkap");
  } else if(j-2>=l) {
    printf("\nOutput : Notasi infix salah, operator tidak lengkap");
  } else {
    stack<int> s;

    string exp;
    puts("");
    cout<<"\n\nUntuk mengetahui hasil\n";
    cout<<"Salin Ekspresi postfix diatas: ";
    cin>>exp;

    //melintasi ekspresi postfix dari kiri ke kanan
    for(int i=0; i<exp.length(); i++) {

      //jika simbol adalah digit, dorong ke dalam tumpukan
      if (isdigit(exp[i]))
        s.push(exp[i] - '0');

      //jika simbol adalah operator maka keluarkan 2 elemen teratas dari tumpukan, lakukan operasi tertentu dan dorong hasilnya kembali ke tumpukan
      else {
        int op2=s.top();
        s.pop();
        int op1=s.top();
        s.pop();

        if(exp[i]=='+')
          s.push(op1+op2);
        else if(exp[i]=='-')
          s.push(op1-op2);
        else if(exp[i]=='*')
          s.push(op1*op2);
        else if(exp[i]=='/')
          s.push(op1/op2);
        else if(exp[i]=='^')
          s.push(pow(op1,op2));
      }
    }
    cout<<"Hasil : "<<s.top();;
  }
}
```
\* note: Not my own code. I respect someone who built those codes.

## Penjelasan
### Latihan 5
```c
if(h!=m) {
  printf("\nOutput : Notasi infix salah, kurung tidak lengkap");
} else if(j==l) {
  printf("\nOutput : Notasi infix salah, operand tidak lengkap");
} else if(j-2>=l) {
  printf("\nOutput : Notasi infix salah, operator tidak lengkap");
}
 ```
 M
## Output
Latihan 5<br>
![image](https://user-images.githubusercontent.com/89684302/159448120-e153e434-7f41-4874-b0a1-e8107b7e00b7.png)


Latihan 6<br>
![image](https://user-images.githubusercontent.com/89684302/159449164-9125dcc3-f177-488e-b85e-0a3bdc06161b.png)



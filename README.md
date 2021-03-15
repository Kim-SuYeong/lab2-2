# lab2-2  
      #include <stdio.h>
      int main()
      {
          printf("[----- [김수영]  [2020039042] -----]\n");
          int i;   //정수형 변수 i
          int *ptr;  //int형 단일 포인터 ptr
          int **dptr; //int형 이중 포인터 dptr

          i = 1234;  //변수 i에 1234대입 

          printf("[checking values before ptr = &i] \n");  
          printf("value of i == %d\n", i);   //i에 저장된 값=1234
          printf("address of i == %p\n", &i); //i의 주소=0061FF1C
          printf("value of ptr == %p\n", ptr); //ptr에 저장된 값=00234000(쓰레기값)
          printf("address of ptr == %p\n", &ptr); //ptr의 주소=0061FF18

          ptr = &i; //ptr이 i의 주소 가리킴

          printf("\n[checking values after ptr = &i] \n");
          printf("value of i == %d\n", i); //i에 저장된 값=1234
          printf("address of i == %p\n", &i); //i의 주소=0061FF1C
          printf("value of ptr == %p\n", ptr); //포인터 ptr이 i의 주소를 가리킴
          printf("address of ptr == %p\n", &ptr); //ptr의 주소=0061FF18
          printf("value of *ptr == %d\n", *ptr); //i의 주소에 저장된 값을 역참조함

          dptr = &ptr; // dptr이 ptr의 주소를 가리킴

          printf("\n[checking values after dptr = &ptr] \n");
          printf("value of i == %d\n", i); //i에 저장된 값
          printf("address of i == %p\n", &i); //i의 주소
          printf("value of ptr == %p\n", ptr); //포인터 ptr이 i의 주소를 가리킴
          printf("address of ptr == %p\n", &ptr); //ptr의 주소=0061FF18
          printf("value of *ptr == %d\n", *ptr); //i의 주소에 저장된 값을 역참조함
          printf("value of dptr == %p\n", dptr); //포인터 dptr이 ptr의 주소를 가리킴
          printf("address of dptr == %p\n", &dptr); //dptr의 주소=0061FF14
          printf("value of *dptr == %p\n", *dptr); //prt의 주소에 저장된 값을 역참조함
          printf("value of **dptr == %d\n", **dptr); //i의 주소에 저장된 값을 역참조함

          *ptr = 7777; // *ptr값 바꿈

          printf("\n[after *ptr = 7777] \n");
          printf("value of i == %d\n", i);   // ptr이 i의 주소를 가리키므로 i의 주소에 7777을 저장하고 
          printf("value of *ptr == %d\n", *ptr); //*ptr이 i의 주소에 저장된 값을 역참조
          printf("value of **dptr == %d\n", **dptr); //*dptr이 *ptr의 주소에 저장된 값을 역참조하여 모두 7777값이 나옴. 

          **dptr = 8888; // **dptr값 바꿈

          printf("\n[after **dptr = 8888] \n");
          printf("value of i == %d\n", i);  // **dprt이 *prt의 주소를 가리키고 *ptr은 i의 주소값을 가리키고 i의 주소에 8888을 저장
          printf("value of *ptr == %d\n", *ptr); //*ptr이 i의 주소에 저장된 값 역참조
          printf("value of **dptr == %d\n", **dptr); //**dptr이 *ptr의 주소에 저장된 값을 역참조하여 모두 8888값이 나옴.

          return 0;
      }

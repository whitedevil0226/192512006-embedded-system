#include <reg51.h>

sbit LED1 = P1^0;

sbit LED2 = P1^1;

void delay()

{

 unsigned int i,j;
 
 for(i=0;i<200;i++)
 
 for(j=0;j<1000;j++);
}


void main()

{

 while(1)
 
 {
 
 LED1 = 1;
 
 LED2 = 0;
 
 delay();
 
 LED1 = 0;
 
 LED2 = 1;
 
 delay();
 
 }

}





output



<img width="1919" height="1013" alt="Image" src="https://github.com/user-attachments/assets/adf0e527-e2cf-4a5c-a567-27fd29630632" />

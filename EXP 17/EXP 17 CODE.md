EXP 17

#include <reg51.h>


void serial_ISR(void) interrupt 4

{

 if(RI)
 
 {
 
 P1 = SBUF;
 
 RI = 0;
 
 
 }

}

void main()

{

 TMOD=0x20;
 
 TH1=0xFD;
 
 SCON=0x50;
 
 TR1=1;
 
 ES=1;
 
 EA=1;
 
 while(1);

}




OUTPUT 



<img width="1909" height="1078" alt="Image" src="https://github.com/user-attachments/assets/36106412-2650-4804-879a-f4e40a21f404" />

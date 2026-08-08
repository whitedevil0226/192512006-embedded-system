EXP 15


#include <reg51.h>


void main(void)

{

 unsigned char hexa = 0x08;
 
 unsigned char hundreds, tens, units;
 
 ACC = hexa;
 
 B = 10;
 
 ACC = ACC / B;
 
 units = B;
 
 B = 10;
 
 ACC = ACC / B;
 
 tens = B;
 
 hundreds = ACC;
 
 P0 = units;
 
 P1 = tens;
 
 P2 = hundreds;
 
 while(1);
}


OUTPUT

<img width="1914" height="1079" alt="Image" src="https://github.com/user-attachments/assets/a3176f7e-666b-48d7-a50d-cb21ec50309e" />

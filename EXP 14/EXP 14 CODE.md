EXP 14

#include <reg51.h> 

#include <stdio.h>

void main (void){

SCON = 0x50; /* SCON: mode 1, 8-bit UART, enable rcvr */ TMOD = 0x20;

/* TMOD: timer 1, mode 2, 8-bit reload */ TH1 = 0xFD; /* TH1: reload

value for 9600 baudrate */

TR1 = 1; /* TR1: timer 1 run */

TI = 1; /* TI: set TI to send first char of UART */ while (1)

{

printf ("Hello World ! \n ");

}

}


OUTPUT


<img width="1919" height="1079" alt="Image" src="https://github.com/user-attachments/assets/714ac860-6257-45d3-971d-379292aef5cb" />

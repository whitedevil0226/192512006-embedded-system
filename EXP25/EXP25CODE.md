EXP 25 


#include <systemc.h>
// Producer Module
SC_MODULE(Producer) {
 sc_fifo_out<int> out;
 void produce() {
 for (int i = 1; i <= 5; i++) {
 cout << "Produced: " << i << endl;
 out.write(i);
 wait(1, SC_SEC);
 }
 }
 SC_CTOR(Producer) {
 SC_THREAD(produce);
 }
};
// Consumer Module
SC_MODULE(Consumer) {
 sc_fifo_in<int> in;
 void consume() {
 int value;
 while (true) {
 in.read(value);
 cout << "Consumed: " << value << endl;
 wait(1, SC_SEC);
 }
 }
 SC_CTOR(Consumer) {
 SC_THREAD(consume);
 }
};
int sc_main(int argc, char* argv[]) {
 sc_fifo<int> fifo(5);
 Producer producer("Producer");
 Consumer consumer("Consumer");
 producer.out(fifo);
 consumer.in(fifo);
 sc_start(10, SC_SEC);
 return 0;
}


<img width="689" height="498" alt="Image" src="https://github.com/user-attachments/assets/b50a50e7-4229-4e4a-ba59-b4d1885179d6" />

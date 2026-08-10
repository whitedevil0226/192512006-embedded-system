EXP 24

#include <systemc.h>
SC_MODULE(ClockExample) {
 sc_in<bool> clk;
 void process() {
 while (true) {
 wait();
 std::cout << "Time: " << sc_time_stamp()
 << " - Clock Triggered" << std::endl;
 }
 }
 SC_CTOR(ClockExample) {
 SC_THREAD(process);
 sensitive << clk.pos();
 }
};
int sc_main(int argc, char* argv[]) {
 sc_clock clock("clock", 1, SC_NS);
 ClockExample module("module");
 module.clk(clock);
 sc_start(5, SC_NS);
 return 0;
}



<img width="1919" height="1075" alt="Image" src="https://github.com/user-attachments/assets/e5189784-8e53-4403-9f6c-3bd917c65220" />

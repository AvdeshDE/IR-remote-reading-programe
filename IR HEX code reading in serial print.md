//# IR-remote-reading-programe
main programe
#include <IRremote.h>
int RECV_PIN = 11;// you can define pin as arduino as well as node mcu in node mcu pin 11 is Tx pin where ir sensor's OUT pin is connected
IRrecv irrecv(RECV_PIN);
decode_results reslults;
void setup()
{
Serial.begin(9600);
irrecv.enableIRIn();  //Start the IR receiver
}
void loop(){
if (irrecv.decode(&results)){
Serial.println(results.value,HEX);//To take HEX CODE of keys of ir remote in serial monitor of you PC. 
irrecv.resume(); //Receive the next value from IR remote when key is pressed. it will show in serial monitor to open serial monitor press Key short cut using (ctrl+M) 
}
}

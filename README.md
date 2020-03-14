# Display-Big

This is a library for Arduino / ESP8266 in order to use a commercially available display (4 digits, or more cascading). It makes you able to show numbers and letters and to do scrolling.

Shows numbers or letters, or scroll alphanumeric string on a big 8888-Display or bigger 88-Display by VisualVision, single or multiple (cascaded); available at 
http://soluzionisemplici.com/8888-display-big/
http://wfeasy.com/8888-display-big/

Hardware:
-----------------------------------------------------
- You can use 4 gpios to have SI SCK RCK PWM or, if you don't have a lot of GPIO available, you can use just SI SCK
- if you don't want to use RCK, put in c.c. the solderjumper RCK-SI and set RCKjoinSI=true
- if you want to set the brightness with a GPIO you can connect this GPIO (let's call it g_pwm) to PWM and use PWM on this pin; if PWM=0 (duty cicle 0) this means full brightness.
 #define PWM_RANGE=512
 analogWrite(g_pwm,255); //set half brightness
- for the ESP that you can solder on board (there is a place for a ESP12E/F) you will use:
 #define g_pwm 16
 #define g_sck 14
 #define g_rck 13
 #define g_si  12


How to use:
-----------------------------------------------------

```cpp

#include <Display-Big.h>

DisplayBig myDisplay(4,g_si,g_sck,g_rck);


void setup(){
  //
  //if you use PWM, you may set range for PWM here
  analogWriteRange(PWM_RANGE-1); //default 0..1023
  analogWriteFreq(40);           //default 1000Hz

}

void loop() {

}

```

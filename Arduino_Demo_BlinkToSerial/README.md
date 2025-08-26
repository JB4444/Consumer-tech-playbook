# Arduino Demo: BlinkToSerial  

This is the **first demo project** in the Consumer Tech Playbook.  
It takes the classic Arduino “Blink” sketch and adds a twist: not only does an LED blink, but your Arduino also sends text updates over the Serial Monitor.  

This is a gentle introduction to firmware — you’ll see how *hardware (the LED)* and *software (the code + serial output)* work together.  

---

## 🔧 What You’ll Learn  

- **What**: How to control an LED with Arduino code, and how to print debug information.  
- **Why**: Blinking LEDs are the “hello world” of embedded systems. Serial printing is the first step toward real debugging and communication with your device.  
- **How**: By combining `pinMode`, `digitalWrite`, and `Serial.print`.  

---

## 🧠 Step 1 — Understanding the Pieces  

- **Arduino Board**: The microcontroller running your code.  
- **LED + Resistor**: The visible output. The resistor prevents too much current from damaging the LED.  
- **USB Cable**: Provides both power and a data connection for serial communication.  

💡 *In consumer tech devices, this same concept shows up in power LEDs, status indicators, or simple debug signals engineers use during prototyping.*  

---

## ⚡ Step 2 — The Circuit  

You’ll connect:  

- Arduino pin **13** → LED (through a resistor) → Ground  
- USB → Computer (for serial connection)  

📂 Files provided:  
- `schematic.png` — simple circuit diagram  
- `breadboard.png` — how it looks on a breadboard  

---

## 💻 Step 3 — The Code  

Here’s what the sketch does:  

```cpp
void setup() {
  pinMode(13, OUTPUT);       // tell Arduino pin 13 will drive an output
  Serial.begin(9600);        // start serial communication at 9600 baud
}

void loop() {
  digitalWrite(13, HIGH);    // turn LED on
  Serial.println("LED ON");  // send message to Serial Monitor
  delay(1000);               // wait 1 second

  digitalWrite(13, LOW);     // turn LED off
  Serial.println("LED OFF"); // send message
  delay(1000);               // wait 1 second
}
```

What’s happening:
- setup() runs once when the board powers up.
- pinMode(13, OUTPUT) sets pin 13 to control an LED.
- Serial.begin(9600) starts serial communication with your computer.
- The loop() then cycles forever: turn LED on/off, print messages, and delay between changes.

## ▶️ Step 4 — Running It

Open BlinkToSerial.ino in the Arduino IDE.
Plug in your Arduino and select the board + COM port.
Upload the sketch.
Open the Serial Monitor (Tools > Serial Monitor).
You should see the LED blink in sync with “LED ON” / “LED OFF” messages scrolling in the window.
✅ You just made your first hardware + software debug tool!

## 📚 Step 5 — Where This Leads

This is just the start. The same skills scale into real consumer devices:
- Serial printing → logging system events in products.
- LED blinking → signaling errors, states, or user feedback.
Inside the Premium Vault you’ll unlock:
- Advanced Arduino labs (UART, I²C, SPI, motor drivers)
- PCB projects that go beyond breadboards
- Full firmware tracks aligned to consumer tech devices

👉 Join the Premium Vault
